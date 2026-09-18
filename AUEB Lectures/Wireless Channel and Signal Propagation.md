---
date: 13/10/25
tags:
  - wireless
  - AUEB
---
## Wireless Networking

Comm. forms that don't require physical contact between transmitter and receiver

- Simplex: One-Way comm. (Radio, TV)
- Half-Duplex: Two-ay comm. NOT simultaneous (Walkie-Talkie)
- Full-Duplex: Two-Way comm. (Cellular Phones)

---
## Multiple hops comm. network

- Wired: Channel independent (0 interference)
- Wireless: Channels can [[interfere]]

---
## Important Terminology

1) Frequency
2) Spectrum
3) Bandwidth
4) Capacity


	1) n° of times wave's peak passes a point in a period of time (Hertz)
	
	2) Set of radio waves used to transport info. 
		   ISM (Industrial Scientific Medical) Band:
		   - Unlicensed (Can be used for free)
		   - EU: 57.00 GHz - 66.00 GHz
		   - US: 57.05 GHz - 64.00 GHz
	   
	   Left to Right Spectrum:
		- Bandwidth $\nearrow$
		- Range $\searrow$ (Attenuation $\nearrow$)
		- Power $\nearrow$
		- Sophisticated Electronics
	
	$\text{3)}$ 
	Frequency: 
		Specific Location on the em spectrum
	 Bandwidth:
		Range between two frequencies
	
	$\text{4)}$ Bandwidth that's fixed for a particular service but with n° of calls and rate of data transmission not (capacity)


> Power: Ability of em wave to persist as it radiates out from the transmitter. Measured in Watts (more conveniently relative to one milliWatt in decibels (dBm))

---
## Propagation

### Signal

![[Pasted image 20251022212315.png|center]]

- Transmission range: 
	- Communication possible
	- Low error rate

- Detection range:
	- Possible detection of signal
	- Impossible communication

- Interference range:
	- Signal may not be detected
	- Signal adds to the background noise


### EM Wave

- Shadowing (through wall/door)
- Refraction depending on density of medium
- Reflection at large obstacles
- Scattering at small objects
- Diffraction at edges

---
## Propagation models

### Free Space Model:

Power of wireless transmission $\searrow$ with square of distance (due to surface area $\nearrow$) 
Reduction depends on wavelength too:
- High wavelength/low frequency = loss $\searrow$
- Small wavelength/high frequency = loss $\nearrow$

$$L=\frac{P_T}{P_R}=(\frac{4πd}{λ})^2=(\frac{4πdf}{c})^2$$

### General Model:

- $L_{d0}$ loss at reference distance $d_0$
$$L_d=L_{d0}*(\frac{d}{d_0})^a$$
$a$: Path loss exponent dependent on environment

| Enviroment              | Value     |
| ----------------------- | --------- |
| Free space              | 2         |
| Urban area cellular     | 2.7 - 3.5 |
| Shadowed urban cell     | 3 - 5     |
| In building LOS         | 1.6 - 1.8 |
| Obstructed in buildings | 4 - 6     |
| Obstructed in factories | 2 - 3     |

### dB and dBm

page 15 of lecture 3


Source: [[Wireless Networks]]

---
Created: 2025-10-13