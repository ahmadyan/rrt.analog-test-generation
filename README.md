rrt.analog-test-generation
==========================

  Randomized Test Generation for Nonlinear Analog Circuits
		Seyed Nematollah Ahmadyan and Shobha Vasudevan

			ahmadyan@gmail.com / shobhav@illinois.edu


	This folder contains the source code and the experimental data
	reported in our manuscript. All of our experiments were performed using MATLAB R2012b on the following machine:
		CPU: Core i5-2500K @3.3GHz
		RAM: 16 GB
		OS: 64bit Windows 8 Pro 


	Folders:
		- rrt: our rrt implementation
		- ode: the MEBDF ODE solver we used for simulating ring modulator
		- vbgm: the implementation of the variational Bayesian inference method by Michael Chen. We utilized the VBGM in our paper in order to infer the distribution of the RRT and goal regions.


	We have three case studies in the RRT folder. 
		1. The josephson junction circuit
		2. The tunnel diode circuit
		3. The ring modulator


	The main script for executing our experiment is the main.m, In our experiments, we usually ran that file several times for different parameters. The script that bootstrap it is script_batch_journal.m

	We saved the data for each run in the .mat file. Loading that file brings up our results. We also saved the corresponding figure in the paper as well. For example, rrt_a_0_5.mat --> rrt_0_5.pdf


	Discrepancy measurement:
	We computed the discrepancy of samples using the star method by Eric Thiemard implemented in sttar_discrepancy.cpp. We wrote our wrapper for that file in discrepancy.cpp This is a matlab mex file. The corresponding wrapper is star.m. We require the MATLAB mex environment (the gcc compiler) to execute that file. For more information take a look at the file star.m

	DAC-2012 implementation
	Our old implementation of the algorithm is available in script_dac.m and datamining.m
