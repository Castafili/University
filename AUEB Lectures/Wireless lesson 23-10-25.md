---
date: 23/10/2025
tags:
  - wireless
  - review
  - AUEB
---
## Multiple Access Systems

- Nodes use common trans. channel
- Collision can happen went two+ hosts send sth simultaneously
- Access Control design problem: limit inefficiencies due to collisions and idle periods 

---
## Multiple Access Control

Protocol used for Ethernet is CSMA/CD (Carrier Sense Multiple Access/ Collision Detect): 
- Waits for idle channel, then send packet
- Stops if collision detected
- Waits random delay post-collision

ALOHA (Less sophisticated than Ethernet):
- Transmits when packet ready
- Stops if collision detected
- Waits random delay post-collision

> Not used in local areas but in metropolitan areas

Token Passing:
- Tokens passed node from node
- Node transmits if it has a token
- Need to be sure token isn't lost + no one node exhibits unfair behavior

---
## Media Access Control (MAC)

Goal: 
- Share a comm. medium among multiple hosts connected to it

Objectives:
- High resource utilization
- Avoid starvation (fairness)
- Simplicity

Solutions:
- Centralized: Better control, simple access logic. Single point of failure, potential bottleneck
- Distributed: Random access
- On demand/Synchronous


page 12 until 18 of slides 4

Source: [[Wireless Networks]]

---
Created: 