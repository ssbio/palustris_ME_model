*******************************************
INSTRUCTION TO RUN THE ME-MODEL IN PYTHON
*******************************************
For any questions, comments, and/or suggestions regarding the steps, please contact Niaz Bahar Chowdhury (nchowdhury2@huskers.unl.edu) 
or Dr. Rajib Saha (rsaha2@unl.edu).
********************************************************************************************************************
For python implementation, the ME-model optimization problem was written using a module named pyomo, and the problem was solved using the GLPK solver.
In this python file, a specific case is simulated with a p-coumarate uptake rate of 2 mmol/gDW/day and the corresponding maximum growth rate of 1.14/day.

Following are the steps which were used to solve the ME-model optimization problem.

STEP 1: Download or install the pyomo module in python. If you are a windows user, type the following command to install the pyomo module

python -m pip install pyomo

STEP 2: Download the GLPK 5.0 solver (http://ftp.gnu.org/gnu/glpk/).

STEP 3: For Windows users, extract the GLPK 5.0 solver and copy the palustris_ME.py and load_model.py to the appropriate directory based on the configuration of 
the computer. For 32 bits computer, the directory is (glpk/w32) and for 64 bits computer, the directory is (glpk/w64).

STEP 4: As the ME-model is a large-scale optimization model, it can exceed the default maximum recursion depth of python. To make sure, it does not exceed the 
maximum recursion depth, in the load_model.py, import the sys module and add the following line.

sys.setrecursionlimit(10**4)

STEP 5: The growth rate can be found in line 2431 of the palustris_ME.py file. Also, the substrate and essential nutrients are listed between lines 25 to 48 
of the palustris_ME.py file. A dictionary (dictionary.txt) is also attached to identify each of the metabolites and reactions of the model.

STEP 6: To update the photosynthetic efficiency for a given substrate, change the right-hand side of constraint m.c3191. In this specific example, p-coumarate 
was used as a substrate and the right-hand side of constraint m.c3191 was changed to 85.4 mmol/gDW/day. Details of photosynthetic efficiency calculations for
different substrates can be found in Alsiyabi et al. 2021 (https://doi.org/10.1016/j.ymben.2021.08.008).

STEP 7: Update the solver folder location in line 20534 and executable file location in line 20536.

STEP 8: Once STEPS 1-7 are completed, the load_model.py can be run to simulate the ME-model of R. palustris.

Thank you. If you have any questions regarding these steps, please send nchowdhury2@huskers.unl.edu or rsaha2@unl.eduan email explaining the issue in detail.