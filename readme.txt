*** PLEASE CITE THIS WORK ***

Ribeiro, A.A.S.T.; Horta, B.A.C.; de Alencastro, R.B.  J. Braz. Chem. Soc., Vol. 19, No. 7, 1433-1435, 2008.

*************************************

MKTOP version 2.2.1

MKTOP is a Perl Script designed to build topologies for GROMACS (4.5.x)

If you are using Linux/Unix, the command line would be:

mktop_2.2.1.pl -i input.pdb -c charges.txt -o topology.top -ff opls

*** INPUT FORMAT *****

From time to time someone contacts me with problems running MKTOP. While I
definitively appreciate any feedback regarding possible bugs, most reported
errors are actually improper input formating. From version 2.0 on, element
symbol on columns 77-78 has been obligatory. IT SHOULD BE RIGHT-JUSTIFIED AND
UPPER-CASE.

***CHARGES ***
The (optional) input file charges.txt contains atomic charges that you must calculate by some method (we recommend using RESP).
This file must have the following syntax:
(number of atom) (charge)

So, if you decide to perform a simulation of sodium chloride in vacuum, the file would be:

1 1.0000
2 -1.000

If you do not provide a charges.txt file we will assume zero charges for all
atoms!!!

The numbering in the files input.pdb and charges.txt must be the same!!!

***FORCEFIELD ***

MKTOP now supports both AMBER03 and OPLS-AA forcefields, so you need to set
the -ff option either to amber or opls

***CONNECTIVITY****
If your PDB file has connectivity information (lines starting with CONECT) you
can use the -conect option set to yes. MKTOP will use this info to determine
bonds, angles and dihedrals. If you do not have this info, you have to set
-conect equal to no so the script will get this info from the distances in
your PDB. 

In the former case pay extra attention to your output. MKTOP will
use distances between atoms to determine bonded pairs. If some of the
distances in your PDB fall outside of the "bonded range", EVERYTHING WILL
FAIL.

***TIPS ***
Do not forget to change the gromacs_dir line in the beginning of the script to your actual path.

If you have never executed anything on your command line, you are supposed to change the permissions of the file mktop_2.0.pl to make it executable:

chmod u+rxw mktop.pl

If you have any questions, send them to andre@aribeiro.net.br

