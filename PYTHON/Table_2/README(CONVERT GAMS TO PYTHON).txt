*******************************************************
INSTRUCTION TO CONVERT GAMS MODEL IN PYTHON PYOMO MODEL
*******************************************************
For any questions, comments, and/or suggestions regarding the steps, please contact Niaz Bahar Chowdhury (nchowdhury2@huskers.unl.edu) 
or Dr. Rajib Saha (rsaha2@unl.edu).
********************************************************************************************************************
To repeat the growth rate result mentioned in Table 2 of the paper, specific Python Pyomo files associated with those growth rate are included in the 
Table_2 folder(https://github.com/ssbio/palustris_ME_model/tree/main/PYTHON/Table_2). Each of the python file can be run using the protocol mentioned in 
the README.txt of this directory(https://github.com/ssbio/palustris_ME_model/tree/main/PYTHON).

In this file step-by-step procedure is discussed on converting the GAMS files to Python Pyomo file.

Following are the steps which were used to convert the GAMS file to Python Pyomo file:

STEP 1: Open the text file "upper_bound.txt" from the folder (https://github.com/ssbio/palustris_ME_model/tree/main/GAMS). The uptake rate of butyrate (line 3),
        succinate (line 6), p-coumarate (line 14), and acetate (line 48) can be set by changing the existing uptake rate. Different uptake rates and associated
		growth rate can be found in the supplementary file Table S2.

STEP 2: From the GitHub page (https://github.com/ssbio/palustris_ME_model/tree/main/GAMS), open the file, palustris_ME.gms. This is GAMS script in which
		information of reactions, and metabolites were incorporated to simulate the ME-model. In line 53, change the growth rate for different substrate uptake
		rates as mentioned in the supplementary file Table S2.

STEP 3: Just after line 8709, add the following:
		"option LP=convert;"
		
STEP 4: Create a file named "convert.opt". Inside the file, add the following line
		"pyomo primal.py"
		
STEP 5: Once the GAMS file, "palustris_ME.gms", is simulated, it will provide a Python Pyomo format file corresponding to the assigned growth rate and associted
		nutrient uptake rate.
		
STEP 6: This Python Pyomo file can be run using the previous README.txt file (https://github.com/ssbio/palustris_ME_model/tree/main/PYTHON).

Thank you. If you have any questions or suggestions regarding these steps, please send nchowdhury2@huskers.unl.edu or rsaha2@unl.eduan email explaining the 
issue/suggestion in detail.