This folder displays the input, output and interpretation of transition metal defects in 4H silicon carbide bigger cluster calculations. 
The software package of AMS (Amsterdam Modeling Suite) with the BAND engine was used. The BAND engine is an atomic-orbital based DFT
engine aimed at periodic systems (crystals, slabs, chains) but supporting also molecular systems.

As our example case, the input and output of VANADIUM are extensively explained. The rest of the systems display similar calculations
with different defects: chromium, niobium, molybdenum, tantalum, tungsten, rhenium. The electron configurations of these defects are:

    V  = [Ar] 4s² 3d³
    Cr = [Ar] 3d⁵ 4s¹
    Nb = [Kr] 5s¹ 4d⁴
    Mo = [Kr] 4d⁵ 5s¹
    Ta = [Xe] 4f¹⁴ 5d³ 6s²
    W  = [Xe] 6s² 4f¹⁴ 5d⁴
    Re = [Xe] 6s² 4f¹⁴ 5d⁵

which after bonding with the neighbouring carbon atoms:

    V  = [Ar] 3d¹
    Cr = [Ar] 3d²
    Nb = [Kr] 4d¹
    Mo = [Kr] 4d²
    Ta = [Xe] 4f¹⁴ 5d¹
    W  = [Xe] 4f¹⁴ 5d²
    Re = [Xe] 4f¹⁴ 5d³

For each defect two type of calculations were carried out for both the geometry optimisations and single point calculations: natural
charge and total charge = 1. The latter forces the defect to have one electron less in the defect. The interest of our research is to
look at systems with only 1 electron in the d-orbital, so we should focus on the following settings and results:

    V       with     natural charge
    Cr      with     total charge = 1
    Nb      with     natural charge
    Mo      with     total charge = 1
    Ta      with     natural charge
    W       with     total charge = 1
    Re      with     total charge = 2

###############
# INPUT FILES #
###############

The input files are taken 