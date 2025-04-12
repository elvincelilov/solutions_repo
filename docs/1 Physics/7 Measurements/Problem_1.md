# Problem 1

### **Problem 1: Measuring Earth's Gravitational Acceleration with a Pendulum**

This task focuses on determining the acceleration due to gravity (denoted as \( g \)) using a simple pendulum and analyzing the uncertainties in the measurements. We'll break this down step-by-step to ensure clear understanding and practical implementation.

---

### **Motivation**
The acceleration due to gravity \( g \) is a fundamental physical constant. Accurate measurements of \( g \) are essential in many scientific fields. One of the most common ways to determine \( g \) experimentally is using a pendulum, where the period of oscillation is dependent on \( g \).

### **Procedure**
1. **Materials Needed:**
   - String (1 or 1.5 meters long)
   - A small weight (e.g., bag of coins, bag of sugar, key chain)
   - Stopwatch (or smartphone timer)
   - Ruler or measuring tape

2. **Setup:**
   - Attach the weight to one end of the string and fix the other end to a sturdy support.
   - Measure the length of the pendulum \( L \) from the suspension point to the center of the weight. Use a ruler or measuring tape. Record the resolution of the measuring tool and calculate the uncertainty in the length \( \Delta L \) (which is half of the resolution of the ruler).
   
3. **Data Collection:**
   - Displace the pendulum slightly (less than 15°) and release it.
   - Measure the time for 10 full oscillations (\( T_{10} \)).
   - Repeat the process 10 times to obtain 10 measurements.
   - Calculate the **mean time for 10 oscillations** \( \langle T_{10} \rangle \) and the **standard deviation** \( \sigma_{T_{10}} \).
   - Determine the **uncertainty in the mean time** using the formula:

     \[
     \Delta T = \frac{\sigma_{T_{10}}}{\sqrt{n}}
     \]

     where \( n \) is the number of measurements.

---

### **Calculations**
1. **Calculate the Period \( T \):**
   - The period \( T \) is the time for a single oscillation. We can find the period from the mean time for 10 oscillations:

     \[
     T = \frac{\langle T_{10} \rangle}{10}
     \]

2. **Determine \( g \):**
   The formula for the period \( T \) of a simple pendulum is:

   \[
   T = 2\pi \sqrt{\frac{L}{g}}
   \]

   Rearranging this formula to solve for \( g \):

   \[
   g = \frac{4\pi^2 L}{T^2}
   \]

3. **Propagate Uncertainties:**
   The uncertainty in \( g \) can be determined using error propagation. The general formula for uncertainty propagation when \( g \) depends on \( L \) and \( T \) is:

   \[
   \Delta g = \sqrt{\left( \frac{\partial g}{\partial L} \Delta L \right)^2 + \left( \frac{\partial g}{\partial T} \Delta T \right)^2}
   \]

   The partial derivatives are:
   - \( \frac{\partial g}{\partial L} = \frac{4\pi^2}{T^2} \)
   - \( \frac{\partial g}{\partial T} = -\frac{8\pi^2 L}{T^3} \)

   Therefore, the uncertainty in \( g \) is:

   \[
   \Delta g = \sqrt{\left( \frac{4\pi^2}{T^2} \Delta L \right)^2 + \left( -\frac{8\pi^2 L}{T^3} \Delta T \right)^2}
   \]

---

### **Analysis**

1. **Compare your measured \( g \) with the standard value**:  
   The standard value of \( g \) at the Earth's surface is approximately **9.81 m/s²**. Compare your calculated value of \( g \) to this standard value and discuss any differences.

2. **Discuss the following aspects:**
   - **Effect of measurement resolution on \( g \)**: Discuss how uncertainties in the measurement of length (e.g., resolution of the ruler) influence the final result.
   - **Variability in timing**: Discuss how timing errors (e.g., human reaction time when using a stopwatch) might affect the precision of the period measurement.
   - **Assumptions and experimental limitations**: For example, we assume the pendulum's oscillations are small enough to approximate the period with the simple formula for a small-angle pendulum. Discuss potential sources of error, such as friction at the pivot point or air resistance.

---

### **Tabulated Data Format (Markdown Example)**

Here’s an example of how you might structure your tabulated data and analysis in a Markdown document:

```markdown
## Pendulum Experiment to Measure Earth's Gravitational Acceleration

### Measured Data

| Trial # | Time for 10 Oscillations (s) | Period for 1 Oscillation (T) (s) | Uncertainty in Time (s) |
|---------|-----------------------------|----------------------------------|-------------------------|
| 1       | 20.3                        | 2.03                             | 0.02                    |
| 2       | 20.1                        | 2.01                             | 0.02                    |
| 3       | 20.5                        | 2.05                             | 0.02                    |
| ...     | ...                         | ...                              | ...                     |

### Calculations

- **Mean Time for 10 Oscillations**:  
  \( \langle T_{10} \rangle = 20.2 \, \text{s} \)
  
- **Period for 1 Oscillation**:  
  \( T = \frac{\langle T_{10} \rangle}{10} = 2.02 \, \text{s} \)
  
- **Length of Pendulum**:  
  \( L = 1.0 \, \text{m} \)
  
- **Calculated Gravitational Acceleration \( g \)**:  
  \[
  g = \frac{4\pi^2 L}{T^2} = 9.81 \, \text{m/s}^2
  \]

### Uncertainty Propagation

- **Uncertainty in Gravitational Acceleration**:  
  \[
  \Delta g = \sqrt{\left( \frac{4\pi^2}{T^2} \Delta L \right)^2 + \left( -\frac{8\pi^2 L}{T^3} \Delta T \right)^2}
  \]

  \( \Delta L = 0.01 \, \text{m}, \Delta T = 0.02 \, \text{s} \)

- **Final Value of \( g \) with Uncertainty**:  
  \( g = 9.81 \pm 0.05 \, \text{m/s}^2 \)

### Discussion

- **Effect of Measurement Resolution**:  
  The uncertainty in the measurement of length affects \( g \) by introducing a small uncertainty in the final result.

- **Timing Variability**:  
  Small human reaction times (if using a manual stopwatch) contribute to timing variability, which impacts the uncertainty in the period \( T \).

- **Experimental Limitations**:  
  Assumptions like the small angle approximation for the pendulum and ideal conditions (no air resistance or friction) affect the accuracy of the measured \( g \).

```

---

### **Conclusion**
By performing this experiment, we can measure Earth's gravitational acceleration \( g \) using a simple pendulum and analyze the uncertainties in the measurement. This approach is a great introduction to experimental physics, uncertainty analysis, and error propagation.

Let me know if you need help with any specific part or further explanation! 😊