---
date: 16/10/2025
tags:
  - graphics
  - AUEB
---
Affine transformations (or linear transformations) have these specifics:

- Additivity: $Φ(p+q)=Φ(p)+Φ(q)$
- Scalar multiplication: $Φ(c*p)=c*Φ(p)$

---
## Transformations 2D

Common Transformations (All invertible):
- Translation: $T(p)= I*p+t$
	- Moving a point
- Rotation: $R(p) = R_θ*P$
	- Rotating a point around the origin
- Scaling: $S(p) = S_{sx,sy}*P$
	- Scaling leads to transformation too
- Shearing: $Sh(p)=Sh_{sx,sy}*P$
	- Shifts one coordinate proportionally to another

---
## Composite Transformation

Transformations that don't consist of a single affine one.
Stacking of operators $Φ \circ Γ(p) = Φ(Γ(p))$

These operations are NOT commutative. You get a different result depending on if you first rotate and then scale compared to if you first scale and then rotate

Source: [[Computer Graphics]]

---
Created: 2025-10-22