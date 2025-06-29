##############################
#  CALCULATIONS' EXLANATION  #
##############################

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

#################################
# STEP 1: optimise the geometry #
#################################

INPUT FILE:

    - INPUT.txt: this is the file submitted to the supercomputer, which includes the details of the job (for Habrok), the module used 
                 to perform the calculation, the folder to allocate the output files, and the specifications for the software programme: 
                 task, atoms' coordinates, lattice vectors, atom bonds' information, the engine specification (BAND), and functional (PBE).


OUUPUT FILES:

    - ams.rkf: this file can be opened with AMSview and plots the evolution of the crystal's optimisation, atoms' coordinates, etc
    - output.xyz: it contains the coordinates of the atoms after the geometry optimisation
    - vanadium_geometry_optimization.inp.o16500502: this is the general output file, it contains all relevant information of the calculation,
    subprocesses, and more information like the band diagram values or converge steps of the self-consistent calculation.


The basic unit cell of 4H-SiC consists of 8 atoms (4 carbons and 4 silicons), and it is periodically repeated in space to create two
supercells: 3x3x3 (216 atoms) and 5x5x2 (400 atoms). Both geometries are optimised, and the supercell with the most localised electron is
chosen. For 5x5x2 the orbitals associated with the 8 lowest energy states have the following electron population:

    (include image in notebook)

And for 3x3x3:

    (include image in notebook)

#########################
# STEP 2: energy levels #
#########################

The 5x5x2 supercell's optimised geometry was used to perform the single point calculations. In order to inspect the orbitals associated to
the energy levels of the defect placed in the crystal, a projected density of states (PDOS) is done. This calculation decomposes the contributions
to the energy diagram by atom and orbital. 

INPUT FILE:

    - INPUT.txt: this is the file submitted to the supercomputer, which includes the details of the job (for Habrok), the module used 
                 to perform the calculation, the folder to allocate the output files, and the specifications for the software programme: 
                 task, atoms' coordinates, lattice vectors, atom bonds' information, the engine specification (BAND), functional (PBE), etc


OUUPUT FILES:

    - OUTPUT: It contains all relevant information of the calculation
    - band.rkf (not in this repository): this is another output file which can be opened with AMSview and helps us plot the PDOS per atoms
    and orbital. It is a very heavy file, around 3 GB, so they are stored in (WHERE)

POST-PROCESS:

    - PDOS_results.ipynb: it shows the plot of the energy levels corresponding to defect, divided in orbital types. It also includes a plot
    with the localisation of the electron in the crystal (it appears to be delocalised, not only inn the defect).