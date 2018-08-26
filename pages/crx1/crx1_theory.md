---
title: CRX1 Theory of Operation
keywords: crx1, description, specifications, specs
summary: "A discussion about how CRX1 works."
sidebar: crx1_sidebar
permalink: crx1_theory
folder: crx1
---

## T/R Switch

The T/R switch is not actually a switch, but a simple tuned circuit used in conjunction with two pairs of anti-parallel diodes. The diodes (D1, D2) keep the maximum signal level from the transmitter at 1.4 Vpp, which protects the front end of the CRX1 from overload. The tuned circuit (C3, L1) keeps out-of-band signals out from the T/R switch to avoid mixing of unwanted signals in the diodes.

## Bandpass Filter

The bandpass filter in the front end of the CRX1 is a singly-terminated double-tuned circuit. The side of the filter connected to the T/R switch is designed to terminate in 50 ohms, while the side connecting to the mixer (Q5) is a high-impedance node. Series capacitor C44 provides an impedance transformation from the high-impedance tank circuit to 50 ohms.

## Mixer

Dual-gate MOSFET Q5 is the active mixer in the CRX1. R22 sets the bias point of Q5, and has an effect on the conversion gain and noise figure. Because the current consumption of Q5 is so small (about 1 mA), the drain load for Q5 can be resistive (R21), which allows for easy impedance matching to the following IF filter. Gate 1 termination resistor R19 helps determine the Q of the preceding bandpass filter. The LO port at gate 2 can be terminated in a high impedance (R18) and can tolerate the external VFO port in parallel with the VXO. The conversion gain of this mixer is approximately 4 dB.

## IF Filter

The IF filter is a common crystal ladder filter constructed from standard-value 4.032 MHz crystals. It was designed for a bandwidth of approximately 400 Hz and a termination of 1k ohms. An L-network was integrated on the end of the filter connected to the IF amplifier to transform the 1k ohm impedance down to the approximately 50 ohms needed for the input of the IF amplifier.

## IF Amplifier

Q2 forms a simple base-biased common-emitter amplifier. Transformer T1 matches the 200 ohm output impedance of the amplifier to the 2.2k ohm input impedance of the product detector following it.

## Product Detector

The CRX1 product detector (Q4) is very similar to the mixer. It has resistive terminations on both gates and the drain, which allows ease of impedance matching. The source is bypassed for audio frequencies with a large capacitor (C25) to give conversion gain. A capacitor on the drain (C26) is rolls off the high frequencies on the output.

## Mute

The mute circuitry consists of pair of MOSFETs used as sequenced switches in the audio path. In normal operation, Q6 is off and Q7 is on, allowing audio to pass to the audio amplifier. When the CRX1 is keyed, VCC is presented at the "Key" node. This turns on Q6 nearly immediately (D4 allows current to flow to the gate of Q6 very quickly), shunting the audio signal to ground. Q8 is also activated, which pulls down the voltage on the gate of Q7 more slowly than Q6 is turned on (due to the RC network of R26 and C30). This ensures that Q6 is turned on before Q7 is turned off, which prevents artifacts on mute. When the CRX1 is unkeyed, the "Key" node returns to a high impedance, 0V state. This bleeds voltage off of the gate of Q6, determined by the rate of RC network R23 and C45. This also turns off Q8, which allows voltage to rise on the gate of Q7 at a rate slower than that of Q6's gate. This has the effect of first turning off Q6, then turning on Q7, which helps to avoid muting artifacts.

## Audio Amplifier

The CRX1 audio amplifier consists of three stages. Q11 is a standard voltage-divider biased common-emitter amplifier. Next is direct-coupled PNP amplifier (Q12), which allows for a simpler circuit and better frequency response from the inter-stage coupling. The final stage is a class-AB power amplifier, consisting of Q15, Q16, and Q17. NPN transistor Q15 is a simple emitter follower used to drive the power amplifier. D7 and D8 give the same voltage drop as the emitters of Q16 and Q17, providing the proper bias to the bases of each transistor and avoiding crossover distortion.

## VXO/BFO

Both of these circuits are standard JFET Colpitts oscillators. The VXO uses two parallel crystals to provide a bit more frequency agility than is available from a single crystal. The VXO is also varactor tuned, by applying a tuning voltage from R1 onto reversed-biased D3, which acts as a varactor in this mode.

## Sidetone Oscillator

A Twin-T type oscillator is used here to produce a nearly pure sine wave near a frequency of 600 Hz. The RC networks R41, R46, C39, C40 and R44, C38, C41 provide low-pass and high-pass filtering to only allow the 600 Hz signal to provide positive feedback to the base of Q13. Keying of the sidetone is provided by Q14. Zener diode D6 is used to keep voltage on the collector of Q13 relatively constant under loading, as the frequency of oscillation does change with voltage supply changes.

## Keying

A very simple keying circuit based on the classic design seen in many QRP transmitters. Grounding the key line biases PNP transistor Q10 to allow current to flow to the "Key" port.

## Power Conditioning

Reverse voltage protection is provided by P-channel enhancement mode MOSFET Q9. If reverse voltage is presented to the CRX1 (making the Q9 drain at ground and the gate at VCC), then Q9 will turn off, protecting the rest of the circuitry. In normal use, the gate of Q9 is at ground and the drain is at VCC, allowing current to flow. D5 is provided to protect the gate of Q9 in the case of overvoltage.

{% include links.html %}
