---
author: Raj
category: MicroControllers
date: '2003-06-28 21:36:08'
layout: post
title: MeasurePulseWidth
---

<pre>

;*** Measure the width of an external pulse with an AVR Mega8
;;
;;   PWM sginal from R/C receiver. One 1-2ms pulse every 20ms.
;;   R/C PWM signal connected to ICP (PortB, Pin0).
;;   Mega8 running at 4Mhz.
;;   Demo code writes lower 8 bits of Timer1/ICR1 to PortD.
;;   Note that if upper 8 bits of ICR1 are not all zero, 
;;   then pulse width exceeds valid range.
;;   -rkumar at hyperreal dot org


.include "m8def.inc"

.org 0x0000				; Reset vector
rjmp reset
.org 0x0005				; Timer1 Capture Event Interupt vector
rjmp TIM1_CAPT



reset:
ldi r16, low(RAMEND)	; Set up stack pointer on reset
out SPL, r16
ldi r16, high(RAMEND)
out SPH, r16

ldi r16, (1<<ICES1)|(1<<CS11)|(1<<CS10)
out TCCR1B, r16			; Set clock prescaler to 32
				; Also set the Input Capture Edge Select bit to 1
				; (trigger on rising edge)

ldi r16, 1<<ICF1
out TIFR, r16			; Clear ICF1, Clear pending interupts.

ldi r16, 1<<TICIE1		; Set bit 4.
out TIMSK, r16			; Enable Timer1 capture event interupt.
sei				; Enable global interupts.

ser r16				; Set all bits in r16.
out DDRD, r16			; Set PortD as output.
cbi DDRB, PB0			; Set PB0 (ICP) as input.


loop:				; Loop forever! Wait for interupt!
rjmp loop



; Timer1 Capture Handler_________________________________________________
TIM1_CAPT:
				; We don't need to perserve registers, since they
				; are not used outside this ISR. But be careful
				; when extending this code. Note that this ISR
				; returns from two different places, depending on ICES1!

;;push r16			; Preserve r16
;;in r16, SREG			; Save MCU status register
;;push r16
						

in r20, ICR1L			; Read Input Capture Register to r20/21
in r21, ICR1H


				; Invert the edge select bit.. This is NOT the best way to do this..
				; We have 32 registers, and we should use them.
				; However, it is unclear right now which registers our main loop
				; will need.

in  r16, TCCR1B			; Read Timer1 Control Register B into r16.
bst r16, ICES1			; Store edge select bit in T.
bld r17, ICES1			; Load edge select bit from T into r17.
com r17				; Invert bits in r17.
bst r17, ICES1			; Store edge select bit in T.
bld r16, ICES1			; Now we have the inverted the edge select bit in r16.
out TCCR1B, r16			; Set Timer1 Control Register with inverted edge select bit.


clr r17
out TCNT1H, r17			; Clear Timer1
out TCNT1L, r17

sbrs r16, ICES1			; In r16, if edge select bit==0 (which means we entered on rising edge)
reti				; then return from interupt and wait for falling edge.


; If we reach this point in the ISR, it means we entered on a negative edge.
; The pulse width is already stored in r20/21.


com r20				; Invert bits (led's connected backwards)
out PORTD, r20			; Write lower 8 bits of Timer1 ICR to PortD


;clr r16			; clearing Timer1 here should be unnecessary	
;out TCNT1H, r16		; clear Timer1
;out TCNT1L, r16

;;pop r16			; Remember this isn't the only place we return from the ISR.
;;out SREG, r16
;;pop r16
reti


</pre>
