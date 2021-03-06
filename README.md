----------------------------------------------------------------------
1) Code overview:
----------------------------------------------------------------------

Author: Vassili Kitsios

This C++ code has been written to perform snapshot POD analysis in serial and in parallel using the VTK data format.

This README file contains installation instructions and an overview of the code. If you are to use this code in your own projects please cite the following documents:

Kitsios, V., Cordier, L., Bonnet, J.-P., Ooi, A. & Soria, J., 2011, On the coherent structures and stability properties of a leading edge separated aerofoil with turbulent recirculation, Journal of Fluid Mechanics, Vol. 683, pp 395-416.
http://journals.cambridge.org/action/displayAbstract?fromPage=online&aid=8378263

Kitsios, V., 2010, Recovery of fluid mechanical modes in unsteady separated flows, PhD Thesis, The University of Melbourne
https://minerva-access.unimelb.edu.au/handle/11343/35705


----------------------------------------------------------------------
2) Installation instructions:
----------------------------------------------------------------------

Prior to compliling this code the following libraries are required on the system:

clapack		http://www.netlib.org/clapack/

VTK		http://www.vtk.org

MPICH		http://www.mcs.anl.gov/research/projects/mpi/mpich1-old/


Once these components are installed see "./Makefile" for details on how to compile the present code.


----------------------------------------------------------------------
3) List of files and directories with brief explanations: 
----------------------------------------------------------------------

drivers/				- directory containing executable directory and Makefile

	/Makefile			- Makefile to jump make executable directory

	/snapshot_pod/			- serial snapshot POD code

	/snapshot_pod_mpi/	 	- parallel snapshot POD code

	/pod_reconstruction/	 	- serial POD reconstruction code

	/pod_reconstruction_mpi/	- parallel POD reconstruction code


include/				- directory containing include files from libraries made from src directory


lib/					- directory containing libraries made from src directory


Makefile				- main makefile

Makefile.in				- input makefile with system specific settings. See "Makefile" for how to create your own "Makefile.in"

makefiles/				- directory containing system specific makefiles


src/					- directory containing the library source directories

	/libUtils/			- directory containing the source for a general Utilities library

	/libPodUtils/			- directory containing the source for the POD library common to all POD driver codes


tests/

	snapsho_pod/			- example of how to set up the input deck and output for a serial snapshot POD run

		pbs-script		- script to launch job on cluster

		snapshot_pod_mpi.in	- input deck containing parameters specifying the job details

	snapsho_pod_mpi/		- example of how to set up the input deck and output for a parallel snapshot POD run

		pbs-script		- script to launch job on cluster

		snapshot_pod_mpi.in	- input deck containing parameters specifying the job details


----------------------------------------------------------------------
