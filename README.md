# README file 
This repository is created to distribute supplementary Molecular Dynamics (MD) data files related to the manuscript of Carabjac *et al.*, submitted to Biophysical Journal. 

## Main Directory
In the main directory, the coordinate file of the pre-equilibrated POPC membrane bilayer (POPCbilayer.pdb) can be found. 
The pre-equilibrated POPC membrane bilayer was constructed using the CHARMM Membrane Bilayer Builder GUI as described in the supplementary materials. 

## Data folders WildType, L1W, V4W, L5W and L7W
These datafolders contain the input coordinates (*.inpcrd) and the parameter (**.prmtop) files of the various (tryptophan-labelled) viscosin molecules on a POPC membrane bilayer. In addition, the input coordinates are also supplied in a *.pdb format.
The starting conformation of viscosin was determined by means of liquid state NMR spectroscopy. In short, the structure was calculated using a simulation annealing approach, based on 109 nOe distance restraints obtained from a DPC micellar solution. The structure was further refined by means of unrestrained molecular dynamics simulations. The structure is currently under review for deposition in the Protein Data Bank (ID 8S2C) and is the subject of a larger study focussing on conformational differences between different cyclic lipodepsipeptides from *Pseudomonas* bacteria. 

## Scripts
The folder 'Scripts' contains the input files as provided to the AMBER software suite to perform the Molecular Dynamics simulations. 
1. minR_PME_cut10.in and
2. min_PME_cut10.in: The first step is essential to minimize and relax the initially generated structure. This method of minimization is fairly common in Amber molecular dynamics simulations.
3. heatR-NVT_PME_cut10.in: After the initial minimization, slowly heat the system to production temperature.
4. hold.in: In order to equilibrate the system's periodic boundary condition dimensions, it is necessary if you are using the GPU code pmemd.cuda, to run 5ns MD with a barostat. The system's dimensions and density must equilibrate before proceeding with production MD. Because the periodic boundary condition box dimensions are changing, it is necessary to increase the "skinnb" value and to restart the MD simulation after 500ns. 
5. MDeqNPT_PME_cut10.in: Production Molecular Dynamics simulation. 

