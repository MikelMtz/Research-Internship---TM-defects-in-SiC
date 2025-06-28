#############
#  CONTENT  #
#############

Each of the folders display the input and output of the geometry optimisations for 3x3x3 and 5x5x2 supercells, together with
single point calculations on the optimised geometry of the 5x5x2 supercell. Two settings are calculated for each defect: one with the 
natural charge, and another one 'taking away' one electron from the defect (it was explained in the README file of the previous folder).

GEOMETRY OPTIMISATION: The Amsterdam Modeling Suite (AMS) performs geometry optimization by iteratively adjusting atomic positions—and
optionally lattice vectors—to minimize the total energy of a system, effectively locating a local minimum on the potential energy 
surface. Using the BAND engine, which is suited for periodic systems, AMS applies Density Functional Theory (DFT) with periodic 
boundary conditions, numerical atomic orbitals, and k-point sampling to compute electronic structure, total energy, forces, and 
stress (if lattice optimization is enabled). It then updates the geometry using optimization algorithms such as L-BFGS or Rational 
Function Optimization, which predict atomic displacements based on gradients and energy changes. This process continues until 
convergence criteria are met, such as thresholds for maximum force, RMS force, energy change, and stress. Upon convergence, AMS 
outputs the optimized atomic coordinates, lattice (if applicable), final energy, and optionally electronic structure properties 
like the band structure or density of states.


SINGLE POINT CALCULATION: In a single point calculation, the Amsterdam Modeling Suite (AMS) computes the total energy and electronic 
structure of a fixed atomic configuration without modifying the atomic positions or lattice parameters. Using an engine like BAND, 
AMS applies Density Functional Theory (DFT) with periodic boundary conditions, numerical atomic orbitals, and k-point sampling to 
solve the electronic structure problem for the given geometry. The calculation yields properties such as total energy, electron 
density, atomic charges, and the electronic density of states or band structure, depending on the settings. Since the geometry remains 
unchanged throughout, no optimization algorithms are used, making single point calculations ideal for analyzing the electronic 
properties of a specific structure, benchmarking, or as a preliminary step before geometry optimization or other simulations.


