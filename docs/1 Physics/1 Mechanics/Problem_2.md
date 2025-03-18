# Problem 2

A four-bar linkage consists of four rigid links connected by four revolute joints, allowing motion transfer between input and output links.

Types of Four-Bar Linkages:
Crank-Rocker Mechanism – One link rotates fully, and another oscillates.
Double Crank Mechanism – Both links rotate completely.
Double Rocker Mechanism – Both links oscillate.
Drag-Link Mechanism – The shortest link is the ground, and both moving links rotate fully.
Key Equations in Four-Bar Linkage
1. Grashof’s Criterion (Mobility Condition)
To determine if at least one link can rotate completely, we use the following condition:

S + L ≤ P + Q

Where:
S = Shortest link
L = Longest link
P, Q = The other two links
If this condition is satisfied, the mechanism allows continuous motion.

2. Velocity Analysis (Relative Velocity Equation)
The velocity of a point on a link can be calculated using the Instantaneous Center Method:

V = ω × r

Where:

V = Linear velocity
ω = Angular velocity
r = Distance from the pivot
For two links in a four-bar mechanism, the ratio of angular velocities is:

ω₂ / ω₁ = L₁ / L₂

Where:

ω₁, ω₂ = Angular velocities of two links
L₁, L₂ = Lengths of the respective links
3. Acceleration Analysis (Coriolis Acceleration)
The total acceleration of a point in a four-bar linkage is the sum of two components:

a = α × r + ω² × r

Where:
a = Acceleration
α = Angular acceleration
ω = Angular velocity
r = Distance from the pivot
For a slider-crank mechanism (a special case of a four-bar linkage), the Coriolis acceleration is:

aᶜ = 2ωv

Where:

aᶜ = Coriolis acceleration
v = Velocity of the slider
4. Transmission Angle (μ)
The transmission angle determines the efficiency of force transfer in the linkage mechanism:

μ = cos⁻¹ [(L₂² + L₃² - L₄²) / (2 L₂ L₃)]

Where:

L₂, L₃, L₄ = Lengths of the links
The best efficiency occurs when the transmission angle μ is close to 90°.

Applications of Four-Bar Linkages
Automobiles – Suspension systems, steering mechanisms
Robotics – Robotic arms, gripper mechanisms
Manufacturing Machines – Punching machines, presses
Bicycles – Pedal mechanisms
