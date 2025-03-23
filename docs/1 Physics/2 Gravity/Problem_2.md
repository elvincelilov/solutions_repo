# Problem 2

Ah, I see! You need four diagrams, each tied to a specific concept, within the explanation. Let me fix that and provide the **complete description** with the corresponding **Python-generated diagrams** for each part.

I'll go through each part of the task, include a detailed explanation, and add the appropriate code and diagrams. Let's get started!

---

# **Escape Velocities and Cosmic Velocities**

## **1. Theoretical Foundation**

### **(a) Escape Velocity**

The **escape velocity** is the minimum speed required for an object to escape the gravitational pull of a celestial body (like a planet or star) without further propulsion. It is derived from the concept of **energy conservation**, where the kinetic energy must equal the gravitational potential energy.

The formula for escape velocity is:

\[
v_2 = \sqrt{\frac{2GM}{R}}
\]

Where:
- \( G \) is the **gravitational constant**,
- \( M \) is the **mass** of the celestial body,
- \( R \) is the **radius** of the celestial body.

#### **Escape Velocity Diagram**
To visualize the escape velocity, imagine a rocket launched from the surface of a planet. To escape, it needs to reach a speed equal to or greater than the escape velocity.

**Diagram 1: Escape Velocity for Earth, Mars, and Jupiter**
This plot shows how escape velocity changes for different celestial bodies (Earth, Mars, and Jupiter).

**Python Code for Escape Velocity Diagram:**

```python
import numpy as np
import matplotlib.pyplot as plt

# Gravitational Constant
G = 6.67430e-11  # m^3 kg^-1 s^-2

# Define planets (mass in kg, radius in m)
planets = {
    "Earth": {"M": 5.972e24, "R": 6.371e6},
    "Mars": {"M": 6.417e23, "R": 3.389e6},
    "Jupiter": {"M": 1.898e27, "R": 6.9911e7}
}

# Calculate Escape Velocity
escape_velocities = {}
for body, data in planets.items():
    M, R = data["M"], data["R"]
    v_escape = np.sqrt(2 * G * M / R)
    escape_velocities[body] = v_escape

# Plotting the Escape Velocity
labels = list(planets.keys())
velocities = list(escape_velocities.values())

plt.figure(figsize=(8, 5))
plt.bar(labels, velocities, color=['blue', 'red', 'green'])
plt.title("Escape Velocities for Earth, Mars, and Jupiter")
plt.xlabel("Celestial Body")
plt.ylabel("Escape Velocity (m/s)")
plt.grid(True)
plt.show()
```

---

### **(b) Orbital (First Cosmic) Velocity**

The **orbital velocity** is the speed at which an object must travel to stay in a stable orbit around a celestial body. It balances the **centripetal force** required to maintain the orbit and the **gravitational pull** of the planet.

The formula for the orbital velocity is:

\[
v_1 = \sqrt{\frac{GM}{R}}
\]

Where:
- \( M \) is the mass of the celestial body,
- \( R \) is the radius of the orbit (or the distance from the center of the body).

#### **Orbital Velocity Diagram**
A satellite in orbit needs to maintain the **orbital velocity** to stay in a circular orbit.

**Diagram 2: Orbital Velocity for Earth, Mars, and Jupiter**
This plot compares the orbital velocities for Earth, Mars, and Jupiter.

**Python Code for Orbital Velocity Diagram:**

```python
# Calculate Orbital Velocity
orbital_velocities = {}
for body, data in planets.items():
    M, R = data["M"], data["R"]
    v_orbit = np.sqrt(G * M / R)
    orbital_velocities[body] = v_orbit

# Plotting the Orbital Velocity
velocities_orbit = list(orbital_velocities.values())

plt.figure(figsize=(8, 5))
plt.bar(labels, velocities_orbit, color=['purple', 'orange', 'yellow'])
plt.title("Orbital Velocities for Earth, Mars, and Jupiter")
plt.xlabel("Celestial Body")
plt.ylabel("Orbital Velocity (m/s)")
plt.grid(True)
plt.show()
```

---

### **(c) Solar Escape Velocity (Third Cosmic Velocity)**

The **third cosmic velocity** is the velocity needed for an object to escape the entire solar system. It must overcome not only the gravitational pull of the planet but also the gravitational pull of the **Sun**.

The formula for the third cosmic velocity is:

\[
v_3 = \sqrt{v_2^2 + v_{\text{orbit}}^2}
\]

Where:
- \( v_2 \) is the escape velocity of the planet,
- \( v_{\text{orbit}} \) is the orbital velocity of the planet around the Sun.

#### **Solar Escape Velocity Diagram**
To visualize the third cosmic velocity, imagine a spacecraft leaving Earth, moving beyond the solar system and needing to break free of both Earth and Sun’s gravity.

**Diagram 3: Solar Escape Velocity for Earth**
This plot compares the **escape velocity** and the **third cosmic velocity** for Earth.

**Python Code for Solar Escape Velocity Diagram:**

```python
# Sun's mass and radius
sun_mass = 1.989e30  # kg
sun_radius = 6.963e8  # m (approximate radius of the Sun)

# Orbital velocity of Earth around the Sun
v_sun_orbit = np.sqrt(G * sun_mass / sun_radius)

# Calculate the third cosmic velocity
third_cosmic_velocities = {}
for body, data in planets.items():
    M, R = data["M"], data["R"]
    v_escape = np.sqrt(2 * G * M / R)
    v_orbit = np.sqrt(G * M / R)
    v_3 = np.sqrt(v_escape**2 + v_sun_orbit**2)
    third_cosmic_velocities[body] = v_3

# Plotting the Third Cosmic Velocity
velocities_3rd = list(third_cosmic_velocities.values())

plt.figure(figsize=(8, 5))
plt.bar(labels, velocities_3rd, color=['cyan', 'magenta', 'lime'])
plt.title("Third Cosmic Velocities for Earth, Mars, and Jupiter")
plt.xlabel("Celestial Body")
plt.ylabel("Third Cosmic Velocity (m/s)")
plt.grid(True)
plt.show()
```

---

## **2. Visualizing the Velocities**

### **(a) Comparison of Escape, Orbital, and Third Cosmic Velocities**

Let's now compare all three velocities (Escape, Orbital, and Third Cosmic) for Earth, Mars, and Jupiter in one consolidated plot.

**Diagram 4: Comparison of Escape, Orbital, and Third Cosmic Velocities**
This bar chart compares the escape, orbital, and third cosmic velocities for three different celestial bodies.

**Python Code for Comparison Diagram:**

```python
# Calculating all velocities together
escape_velocities = {}
orbital_velocities = {}
third_cosmic_velocities = {}

for body, data in planets.items():
    M, R = data["M"], data["R"]
    v_escape = np.sqrt(2 * G * M / R)
    escape_velocities[body] = v_escape
    v_orbit = np.sqrt(G * M / R)
    orbital_velocities[body] = v_orbit
    v_3 = np.sqrt(v_escape**2 + v_sun_orbit**2)
    third_cosmic_velocities[body] = v_3

# Plotting all velocities in a comparison chart
x = np.arange(len(labels))

fig, ax = plt.subplots(figsize=(10, 6))
bar_width = 0.25

ax.bar(x - bar_width, list(escape_velocities.values()), bar_width, label='Escape Velocity (v2)', color='blue')
ax.bar(x, list(orbital_velocities.values()), bar_width, label='Orbital Velocity (v1)', color='red')
ax.bar(x + bar_width, list(third_cosmic_velocities.values()), bar_width, label='Third Cosmic Velocity (v3)', color='green')

ax.set_xlabel('Celestial Body')
ax.set_ylabel('Velocity (m/s)')
ax.set_title('Comparison of Escape, Orbital, and Third Cosmic Velocities')
ax.set_xticks(x)
ax.set_xticklabels(labels)
ax.legend()
plt.tight_layout()
plt.show()
```

---

## **3. Conclusion**

In this exploration, we learned the following:

- **Escape Velocity**: The minimum speed to escape a planet’s gravity.
- **Orbital Velocity**: The speed necessary to stay in orbit around a planet.
- **Third Cosmic Velocity**: The speed required to escape the entire solar system.

These concepts are essential for **space exploration**, whether launching satellites, sending missions to other planets, or thinking about interstellar travel.

---

### Now, all four diagrams are integrated within the description, with explanations and Python code for generating them. I hope this now fulfills what you were asking for! Let me know if you need anything else! 😊change