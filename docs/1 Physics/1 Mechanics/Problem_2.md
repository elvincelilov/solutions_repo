# Problem 2

A four-bar linkage is one of the simplest and most widely used mechanisms in machines. It consists of four rigid links connected by four revolute joints, allowing motion transfer between input and output links.

Types of Four-Bar Linkages:
Crank-Rocker Mechanism – One link rotates fully, while another oscillates.
Double Crank Mechanism – Two links rotate completely.
Double Rocker Mechanism – Both links oscillate.
Drag-Link Mechanism – The shortest link is the ground, allowing full rotation of both moving links.
Key Equations in Four-Bar Linkage
1. Grashof’s Criterion (Mobility Condition)
To determine if at least one link can rotate completely, we use:

𝑆
+
𝐿
≤
𝑃
+
𝑄
S+L≤P+Q
Where:

𝑆
S = Shortest link
𝐿
L = Longest link
𝑃
P, 
𝑄
Q = Other two links
If this condition is satisfied, the mechanism allows continuous motion.

2. Velocity Analysis (Relative Velocity Equation)
Using the Instantaneous Center Method, the velocity of a point on a link is given by:

𝑉
=
𝜔
×
𝑟
V=ω×r
Where:

𝑉
V = Linear velocity
𝜔
ω = Angular velocity
𝑟
r = Distance from the pivot
For two links in a four-bar mechanism, we use:

𝜔
2
𝜔
1
=
𝐿
1
𝐿
2
ω 
1
​
 
ω 
2
​
 
​
 = 
L 
2
​
 
L 
1
​
 
​
 
Where:

𝜔
1
,
𝜔
2
ω 
1
​
 ,ω 
2
​
  = Angular velocities of two links
𝐿
1
,
𝐿
2
L 
1
​
 ,L 
2
​
  = Lengths of the respective links
3. Acceleration Analysis (Coriolis Acceleration)
The acceleration of a point in a four-bar linkage is:

𝑎
=
𝛼
×
𝑟
+
𝜔
2
×
𝑟
a=α×r+ω 
2
 ×r
Where:

𝑎
a = Acceleration
𝛼
α = Angular acceleration
𝜔
ω = Angular velocity
𝑟
r = Distance from the pivot
For a slider-crank mechanism (a special case of four-bar linkage), the Coriolis acceleration is given by:

𝑎
𝑐
=
2
𝜔
𝑣
a 
c
​
 =2ωv
Where:

𝑎
𝑐
a 
c
​
  = Coriolis acceleration
𝑣
v = Velocity of the slider
4. Transmission Angle (𝛍)
The transmission angle determines the efficiency of force transfer:

𝜇
=
cos
⁡
−
1
(
𝐿
2
2
+
𝐿
3
2
−
𝐿
4
2
2
𝐿
2
𝐿
3
)
μ=cos 
−1
 ( 
2L 
2
​
 L 
3
​
 
L 
2
2
​
 +L 
3
2
​
 −L 
4
2
​
 
​
 )
where:

𝐿
2
,
𝐿
3
,
𝐿
4
L 
2
​
 ,L 
3
​
 ,L 
4
​
  = Link lengths
The best efficiency occurs when 𝛍 is close to 90°.

Applications of Four-Bar Linkages
Automobiles – Suspension systems, steering mechanisms
Robotics – Robotic arms, gripping mechanisms
Manufacturing Machines – Punching machines, presses
Bicycles – Pedal mechanisms