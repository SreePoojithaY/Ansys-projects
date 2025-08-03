ANSYS HFSS Simulation: SAR and Electric Field Around a Transmitter Coil
Project Overview
This project involves the simulation of an RF transmitter coil in ANSYS HFSS 2024 R2 student version to evaluate the Specific Absorption Rate (SAR) and the electric field distribution around the coil. The model features a spiral coil with a rectangular cross-section, placed near a human head model to assess how electromagnetic fields interact with the human body. This simulation is useful for understanding the safety and performance characteristics of RF devices, particularly in medical and communication applications.

Software and Version
Software: ANSYS HFSS 2024 R2
Application: RF and microwave simulations, SAR analysis

Simulation Setup
1. Model Creation:
Coil Geometry: A rectangular helix is created using ANSYS HFSS's user-defined primitives. This type of coil is chosen for its simple and customizable geometry. Parameters include:

Conductor Height: Set to 3 mils (approximately 0.0762 mm), representing a typical copper conductor used in RF coils.

Conductor Width: Set to 67 mils (approximately 1.7 mm).

Start Radius: The radius from the center to the first trace is set to 40 mm.

Pitch (Spacing between Turns): Set to 87 mils (approximately 2.2 mm) to provide spacing between the turns.

Number of Turns: Arbitrarily set to 10 turns.

Material: The coil is modeled using copper as the conductor material, which has a high conductivity suitable for RF applications.

2. Simulation Region:
A vacuum region (airbox) is created around the coil to define the simulation domain. The size of the airbox is set to 1 meter (1000 mm) in all directions to ensure sufficient space for accurate field propagation analysis.

The boundary condition of the airbox is set to a radiation boundary, which assumes that the radiated fields extend infinitely beyond the airbox, typically used for antenna simulations.

3. Human Head Model:
A human head model is imported from the materials library to simulate the effect of the coil’s electromagnetic fields on human tissue.

The material properties of the head are set to human average with a relative permittivity of 1.0 (can be adjusted for more realistic simulations based on specific tissue types).

The head is placed approximately 15 mm below the coil to simulate the interaction between the coil and a real-world human subject.

4. Current Source Setup:
A current source is applied to the coil by creating a conductive sheet that bridges the open loop of the coil. The current flow is set to be in the Z-direction, and the magnitude is set based on a 1 A RMS current (converted to peak current for simulation purposes).

5. Meshing:
A mesh is generated for the coil and the surrounding vacuum region. The mesh density is set to 20 mm maximum element length for the coil and the surrounding region. For higher accuracy near the coil, a smaller mesh size could be applied, though it increases computational time and memory usage.

A refinement technique can be used in regions of interest, such as close to the coil, to achieve better resolution of the fields.

Simulation Parameters
Frequency: 300 kHz (chosen for its relevance to RF coil applications).

Solver Type: Iterative solver (preferred for lower memory usage on personal computers).

Convergence Criteria: The simulation is set to converge with a max Delta energy of 0.1% and to run for a minimum of 5 passes to ensure stable results.

Adaptive Passes: Set to 110 passes for the solution to fully converge, ensuring the electromagnetic field is accurately solved.

Results
1. Electric Field Distribution:
Electric Field Plots: The electric field (E-field) is calculated in the region around the coil and the head. The electric field strength is shown to be strongest near the coil and diminishes as the distance increases.

E-field Convergence: The electric field along a defined Z-axis line was tracked throughout the simulation, showing a smooth and predictable decay from the coil.

2. SAR Distribution:
SAR Calculation: The Specific Absorption Rate (SAR) is computed inside the head model. The SAR values are highest near the coil and decrease with increasing distance from the coil.

SAR Hotspots: The SAR heatmap reveals the regions within the head where the highest energy absorption occurs, which is essential for ensuring the safety limits for RF exposure in medical devices.

Max SAR Values: The peak SAR for different coil orientations (0°, 90°, etc.) is calculated. The highest SAR values are recorded when the coil is directly aligned with the head.

3. Parametric Sweep:
A parametric sweep was performed to rotate the coil and head relative to each other in steps of 30° (0° to 270°). This sweep helps determine the SAR variability and E-field distribution as the coil rotates, simulating a real-world scenario where the coil might move or rotate during use.

Results show variation in SAR with coil orientation, providing insight into the coil's performance and safety across different angles.

4. Results Visualization:
Electric Field Plot: The electric field distribution on a YZ-plane is visualized, showing how the field varies in different regions around the coil.

Magnetic Field Plot: The MAgnetic field distribution on a YZ-plane is visualized, showing how the field varies in different regions around the coil.

SAR Heatmap: A heatmap of the SAR distribution on the human head is generated, identifying potential hot spots that could lead to safety concerns.

Conclusion
This ANSYS HFSS simulation successfully models the behavior of a transmitter coil and its interaction with the human head, providing insights into the electric field distribution and SAR values. The parametric sweep and results visualization techniques are crucial for understanding how coil orientation affects field strength and safety, which is essential in applications like medical RF devices and communication systems.

The findings from this simulation can be used to optimize coil design for both performance and safety, ensuring that SAR values remain within regulatory limits for human exposure.
