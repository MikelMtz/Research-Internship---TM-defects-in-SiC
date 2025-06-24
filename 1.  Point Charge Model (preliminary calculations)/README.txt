The present calculations show the results of the Point Charge Model for 4 point charges distributed around a defect in C3v symmetry.

The relativistic effects can be supressed in the calculation, which has two parts:

    - The crystal field
    - The spin-orbit coupling

The relativistic effects can be supressed in both parts, or just in one of them independently.

For the crystal field the keyword CLIG can be used, whereas the spin-orbit (inherently relativistic) can be supressed by changing 
fundamental constants from the source code. The latter will be explained in a separate file.

###################
#   INPUT FILES   #    --> The files inside Input files folder are examples of the input to 
###################        run the calculations for this part of the project

The Input.txt contains the keywords and structure to run a OpenMolcas calculation.

The Sbatch.txt file is the one to be submitted to the cluster. This can be done by typing in the terminal >> sbatch JOB
It contains the details of the job: how much are we assigning to it, how many resources, its name, folder to be located,
location of the executable, variables to be used in the JOB file (if needed).

NOTE: The .txt extensions of the files should be taken out when run in the cluster, they are just convenient to display them in this 
environment. 


######################################
#   Supressing Spin-Orbit coupling   #
######################################

In order to suppress the spin-orbit coupling in the calculations, the fine strucure constant in the source has to be changed.
This can be done by accesing the OpenMolcas programm given in 'Resources' folde and accesing ...