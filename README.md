# KNN_Plot
This assignment puts the known points a and b on the scatter plot and the unknown points "?" on the plot as well. 
Then it finds the K nearest neighbors using Euclidean distance, manhattan distance, and chessboard distance.
I have it set for 5 neighbors currently, but that could be changed to whatever is most desirable. 
The program prints the nearest neighbors and whether they are a or b, to estimate what the unknown "?" point would be. 

Sources used:
  (Most of the sources I used were refreshes and reminders on syntax, but source  # C I followed a tutorial to see the syntax for Euclidean distance. This tutorial was super helpful because as I already knew the Euclidean Distance formula, I was a little iffy on the  syntax to find all the nearest neighbors(smallest distances). I also played around adding weights to the formula on another program, which was not needed for this program scope.)
  
    # A: to label a single point on a scatter plot - https://www.kite.com/python/answers/how-to-label-a-single-point-in-a-matplotlib-graph-in-python
    # B: matplot and general scatter plot refresher - https://pythonspot.com/matplotlib-scatterplot/
    # C: used Euclidean distance code tutorial from: https://machinelearningmastery.com/tutorial-to-implement-k-nearest-neighbors-in-python-from-scratch/
    # D: for x in range(len(a)): syntax: https://snakify.org/en/lessons/two_dimensional_lists_arrays/
    # E: chessboard distance: https://reference.wolfram.com/language/ref/ChessboardDistance.html
