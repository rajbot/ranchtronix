---
author: Raj
category: TikiCrawler3000
date: '2003-08-20 04:47:19'
layout: post
title: LinearActuatorControl
---

<pre>

;*** Measure the width of an external pulse with an AVR Mega8
;;
;;   PWM sginal from R/C receiver. One 1-2ms pulse every 20ms.
;;   R/C PWM signal connected to ICP (PortB, Pin0).
;;   Mega8 running at 4Mhz.
;;   Demo code sets C0/C1 to move linear actuator left or right.
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
sei						; Enable global interupts.

ser r16					; Set all bits in r16.
out DDRD, r16			; Set PortD as output.
;out DDRB, r16			; Set PortB as output.
out DDRC, r16			; Set PortC as output (instead of PortB!)

cbi DDRB, PB0			; Set PB0 (ICP) as input.


loop:					; Loop forever! Wait for interupt!
rjmp loop



; Timer1 Capture Handler_________________________________________________
TIM1_CAPT:
						; We don't need to perserve registers, since they
						; are not used outside this ISR. But be careful
						; when extending this code. Note that this ISR
						; returns from different places!



in r20, ICR1L			; Read Input Capture Register to r20/21
in r21, ICR1H


						; Invert the edge select bit.. This is NOT the best way to do this..
						; We have 32 registers, and we should use them.
						; However, it is unclear right now which registers our main loop
						; will need.

in  r16, TCCR1B			; Read Timer1 Control Register B into r16.
bst r16, ICES1			; Store edge select bit in T.
bld r17, ICES1			; Load edge select bit from T into r17.
com r17					; Invert bits in r17.
bst r17, ICES1			; Store edge select bit in T.
bld r16, ICES1			; Now we have the inverted the edge select bit in r16.
out TCCR1B, r16			; Set Timer1 Control Register with inverted edge select bit.


clr r17
out TCNT1H, r17			; Clear Timer1
out TCNT1L, r17

sbrs r16, ICES1			; In r16, if edge select bit==0 (which means we entered on rising edge)
reti					; then return from interupt and wait for falling edge.


; If we reach this point in the ISR, it means we entered on a negative edge.
; The pulse width is already stored in r20/21.

cpi r21, 0				; compaire r21 with 0
    brne case_rcerror		;    if not zero, then handle error
cpi r20, 128			; else, compare r20 with 128
    brsh case_rcerror		;    if greater or equal than 128, then handle error 
cpi r20, 66				; else, compare r20 with 66
    brlo case_right		;    if less than6, move actuator right
cpi r20, 102			; else, compare r20 with 102
    brsh case_left			; if same or higher than 102, move actuator left
default:				; else...
    cbi PORTC, PC1			; clear PB2 and PB4...
    cbi PORTC, PC0			; ...to ensure the actuator is not moving!
    com r20				; Invert bits (led's connected backwards)
    out PORTD, r20			; Write lower 8 bits of Timer1 ICR to PortD


;clr r16				; clearing Timer1 here should be unnecessary	
;out TCNT1H, r16		; clear Timer1
;out TCNT1L, r16

reti



; case_right: Move the Linear Actuator to the right______________________
case_right:
cbi PORTC, PC0			; Ensure that PB4 is not set
sbi PORTC, PC1			; Set PB2 to move the actuator right.

com r20					; Invert bits (led's connected backwards)
out PORTD, r20			; Write lower 8 bits of Timer1 ICR to PortD
reti


; case_left: Move the Linear Actuator to the left________________________
case_left:
cbi PORTC, PC1			; Ensure that PB2 is not set
sbi PORTC, PC0			; Set PB4 to move the actuator left.

com r20					; Invert bits (led's connected backwards)
out PORTD, r20			; Write lower 8 bits of Timer1 ICR to PortD
reti


; case_rcerror: Handle RC receiver errors________________________________
case_rcerror:
cbi PORTC, PC0
cbi PORTC, PC1

clr r16;
out PORTD, r16;
reti

</pre>
