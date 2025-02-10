# MD-Electrolyte-Simulation

############################### Description ###############################

Coarse-grained molecular dynamics simulation of LiPF6 electrolyte in implicit solvent including a nano-porous separator with charged SO3- functional groups.

############################### Dependencies ###############################

0. LAMMPS Installation (https://docs.lammps.org/Install.html)

1. Membrane_LJ_Coul.in

2. Minimization_LJ_Coul.in

3. PARM.lammps

4. "res" folder

5. "prop" folder

6. "xyz" folder

############################### Executing Program ###############################

1. Make sure all dependencies are in same directory

2. Run Energy Minimization Step: 
	a. Run: 
		lmp_serial -in Minimization_LJ_Coul.in -var Nsalt 10 -var L 30 -var r 14 -var Ngroups 20 -var tr 1 -var SEED1 12345

	b. Parameters: Nsalt - # of LiPF6 molecules | L - box length (Angstrom) | r - pore size (Angstrom) | Ngroups - # of functional groups | tr - trajectory number | SEED1 - random seed 

	c. Should Output: 
		i. "res/Min_...dat" - simulation restart file
		ii. "xyz/Min...xyz" - simulation visualization file

3. Run main simulation:

	a. Run: 
		lmp_serial -in Membrane_LJ_Coul.in -var Nsalt 10 -var L 30 -var r 14 -var tr 1 -var SEED1 643543  

	b. Parameters: *Same as above*
	
	c. Should output:
		i. "xyz/LimEquil...xyz" - simulation visualization file 
		ii. "prop/Etot...txt" - total energy of system through time
		iii. "prop/MSD...txt" - average mean-square displacement of all mobile ions

############################### Help ###############################

Ask DJ (dejuante1503@gmail.com) 
