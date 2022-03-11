# DimLessEnthalpyCalculator
<<<<<<< Updated upstream
## Usage
Put thermodynamic Data inside the .ini file according to comments.
Start the Notebook. Under USER INPUT, define Setup. Calculate.

Change the variable "WorkingAlloy" to a name defined by the .ini file.
Choose a filename for export.

# Search Definition
The algorithm looks for specific Hann Values inside a defined Range. The definition of this range is done with "binsLower" and "binsUpper." The resolution is what difference should be resolveable. For example, 20.05 and 20.06 are the same if the resolution is 0.1.

Parameters for consideration are entered via "_Lower", "_Upper," and "_Stepsize ". Be mindful that the Spot size is defined as the 1/e^2 diameter and needs to be entered in µm.

# Manual Calculation
After one calculation, all functions are defined, and manual calculation can be utilized. Just enter the desired "man_" parameters and calculate. 
"manEnergy" is the Hann number. "manEnergy100" is the Hann number if considering 100% absorption. "manThreshold" is the theoretical Hann number needed for the aspect ratio of the melt pool to become 1. Therefore Hann numbers above this number should yield Keyholes.
"ManEnergy-man thrash" is the difference of the Hann number to the threshold. If it is negative, the Energy is theoretically insufficient to form a keyhole.
"FabbroRatio" is the expected aspect ratio of the melt pool.

# How it works
A range is defined by "binsLower", "binsUpper" and "binsResolution" and Partitioned in lists of three. Therefore all desired Hann enthalpies are defined. The three values inside the list define what the search considers equal.
A Range of possible Parameters is defined next. All parameter combinations are passed to the main function that calculates the Hann number (see "sol"). For all defined bins to search in, the list sol is scanned, and the positions of solutions are returned. A random solution is picked. The position of the randomly picked solution encodes the parameter set. A random solution inside the bin space is chosen. Example: randomsol = {11,1,3} this means that powerlst[[11]],speedlst[[1]] and spotsizelst[[3]] yield the picked solution for the current bin (example search for Hann numbers in bin {1,1.5,2}.
Because it is more accessible to code, the three values are taken and calculated again. The results are appended to a list. The loop repeats until all bins have been analyzed.

=======
Calculating the Dimensionless Enthalpy in LPBF according to Hann / Fabbro. 
- No Approximation of g(Pe) via a linear Function
    - Numerical solution wherby the sum is approximated via the first 100 terms. Convergence can be shown
    
>>>>>>> Stashed changes
