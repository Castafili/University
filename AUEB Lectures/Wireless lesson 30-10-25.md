---
date: 30/10/25
tags:
  - wireless
  - review
  - AUEB
---

## CSMA (Carrier Sense Multiple Access)

Carrier Sense: "Listen before talking"

- Sender:
	- Listen for clear medium
	- If medium idle:
		- Whole frame gets transmitted
		- Start timeout and wait for [[ACK]]
		
	- If medium busy: 
		- Defer transmission

- Receiver: Send [[ACK]] if packet received correctly

---
## CSMA Persistence Schemes


![[Pasted image 20251030095828.png|center]]


- 1-persistent:
	- If two or more stations waiting to transmit a collision is guaranteed
	
- Non-persistent:
	- Probability of collisions $\searrow$
	- Wasted idle time before transmission
	
- p-persistent:
	- How is p selected? Must be Np<1
	- Np>1 instability, Np<<1 unnecessarily long delays


---

## TITLE



Source: [[Wireless Networks]]

---
Created: 2025-10-30