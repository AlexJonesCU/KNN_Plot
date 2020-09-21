# Alex Jones
# 2290441
# scatter plot with a, b, and mystery points

#sources used:
    # A: to label a single point on a scatter plot - https://www.kite.com/python/answers/how-to-label-a-single-point-in-a-matplotlib-graph-in-python
    # B: matplot and general scatter plot refresher - https://pythonspot.com/matplotlib-scatterplot/
    # C: used Euclidean distance code tutorial from: https://machinelearningmastery.com/tutorial-to-implement-k-nearest-neighbors-in-python-from-scratch/
    # D: for x in range(len(a)): syntax: https://snakify.org/en/lessons/two_dimensional_lists_arrays/
    # E: chessboard distance: https://reference.wolfram.com/language/ref/ChessboardDistance.html

import matplotlib.pyplot as plt
from math import sqrt


x = [1,1,-2,-2,1,2,-4,4,2]
y = [0,1,4,-2,3,5,-5,5,-1]

labels = ['a','b','a','b','a','a','a','b','b']


#unknowns
unknown_x = [0,-2,5]
unknown_y = [0,0,5]
u_labels = ['?','?','?']

# points in the plane that we know their label
for i in range(9):
    if labels[i] == 'a':
        plt.scatter(x[i], y[i], color = 'red') #all a points will be red
    elif labels[i] == 'b':
        plt.scatter(x[i], y[i], color = 'blue') # all b points will be blue
    else:
        print("error") # if there is a point not labeled a or b, print error

    plt.annotate(labels[i], (x[i]+.1, y[i]-.3)) #labels the points with their letter, the .1 is for readability

# plotting the unknown points
plt.scatter(unknown_x, unknown_y, color = 'grey')
for u in range(3):
    plt.annotate(u_labels[u], (unknown_x[u]+.1, unknown_y[u]-.3))


plt.title('Exercise 2.3')
plt.xlabel('feature x')
plt.ylabel('feature y')

plt.show()

# ------ FIND K's ---------
#points in x,y format
dataset = [[1,0,'a'],
	[1,1,'b'],
	[-2,4,'a'],
	[-2,-2,'b'],
	[1,3,'a'],
	[2,5,'a'],
	[-4,-5,'a'],
	[4,5,'b'],
	[2,-1,'b']]

unknowns = [[0,0,'?'],
    [-2,0,'?'],
    [5,5,'0']]

#no weights needed

    #Euclidean_Distance = sqrt(sum i to N(x1_i-x2_i)^2)
    #WEIGHTED_Euclidean_Distance = sqrt(sum i to N( w (x1_i-x2_i) )^2)

def euclidean_distance(row1, row2): #source C
    distance = 0.0
    for i in range(len(row1)-1):
        distance += (row1[i] - row2[i])**2 #sum of sqrt of x-y
    return sqrt(distance)

def get_neighbors(train, test_row, num_neighbors): #source C
	distances = list()
	for train_row in train:
		dist = euclidean_distance(test_row, train_row)
		distances.append((train_row, dist))
	distances.sort(key=lambda tup: tup[1])
	neighbors = list()
	for i in range(num_neighbors):
		neighbors.append(distances[i][0])
	return neighbors

    #Manhattan_Distance = sqrt(sum i to N(x1_i-x2_i)^2)
def Manhattan_distance(row1, row2):
    distance = 0.0
    for i in range(len(row1)-1):
        distance += (abs(row1[i] - row2[i])) # sum of absolute val of x-y
    return (distance)

def get_M_neighbors(train, test_row, num_neighbors):
	distances = list()
	for train_row in train:
		dist = Manhattan_distance(test_row, train_row)
		distances.append((train_row, dist))
	distances.sort(key=lambda tup: tup[1])
	m_neighbors = list()
	for i in range(num_neighbors):
		m_neighbors.append(distances[i][0])
	return m_neighbors


def Chessboard_distance(row1, row2):
    distance = 0.0
    distance = max(abs(row1[0] - row2[0]), abs(row1[1]-row2[1])) #max distance
    return (distance)

def get_chess_neighbors(train, test_row, num_neighbors):
	distances = list()
	for train_row in train:
		dist = Chessboard_distance(test_row, train_row)
		distances.append((train_row, dist))
	distances.sort(key=lambda tup: tup[1])
	m_neighbors = list()
	for i in range(num_neighbors):
		m_neighbors.append(distances[i][0])
	return m_neighbors



for point in range(len(unknowns)):
       ## prints the K nearest neighbors based on Euclidean metrics
    print("nearest neighbors of point", unknowns[point])
    print('Euclidean Distance:')

    neighbors = get_neighbors(dataset, unknowns[point], 5) #training data, test row, and number of neighbors wanted
    for neighbor in neighbors:
    	print(neighbor)

       ## prints the K nearest neighbors based on Manhattan metrics
    print('Manhattan Distance:')

    neighbors = get_M_neighbors(dataset, unknowns[point], 5) #training data, test row, and number of neighbors wanted
    for neighbor in neighbors:
    	print(neighbor)

       ## prints the K nearest neighbors based on Chessboard metrics
    print('Chessboard Distance:')

    neighbors = get_chess_neighbors(dataset, unknowns[point], 5) #training data, test row, and number of neighbors wanted
    for neighbor in neighbors:
    	print(neighbor)



    print('_________________________________________')
