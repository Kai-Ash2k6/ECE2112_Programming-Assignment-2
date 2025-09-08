# ECE2112_Programming-Assignment-2
Advance Computer Programming - S.Y. '24-'25  Name: K. A. Gas*ng-n || Section: 2 ECE - C

----- Contents of this Assignment ----- 
    
    1. NumPy Array Normalization – A program that generates a random 5x5 NumPy array, calculates its mean and standard deviation, normalizes the data, and saves the result to a file.
    2. Divisible-by-3 Array Generator – A program that finds the first 100 perfect squares divisible by 3 and arranges them into a 10x10 two-dimensional array.   
---------------- Notes ----------------
    
    - I debugged my code multiple times and used module notes, YouTube tutorials, and 
      other online references to understand  concepts I was not confident with.
    - This repository is part of my journey in learning basic Python programming

 .... Analysis / Notes .....
    
    1. NumPy Array Normalization
    - This program creates a 5x5 random NumPy array using np.random.rand().
    - It calculates the mean and standard deviation of the array using X.mean() and X.std().
    - The array is normalized using the formula:
        𝑍 = (𝑋 − mean) / std
	​  - The normalized array is then saved in a file named X_normalized.npy using np.save().
     - Generalization / Conclusion:
          This program demonstrates how NumPy can handle numerical data efficiently, making operations like normalization simple and faster compared 
          to manual loops. Data normalization is essential in data science, machine learning, and statistical computations

    2. Divisible-by-3 Array Generator
    - This program finds the first 100 perfect squares that are divisible by 3.
    - It uses a while-loop to keep generating squares until 100 valid numbers are found.
    - The numbers are then stored inside a 10x10 2D list (matrix) using nested for-loops.
    - Finally, the program prints the array neatly row by row.
    - Generalization / Conclusion:
          This problem demonstrates the power of loops and list manipulation in Python. It also shows how to structure data into a matrix format, 
          which is useful in numerical computing, simulations, and data organization.


 .... Mini Tutorial .....

## ** Problem 1: NumPy Array Normalization **

Step 1 — Import NumPy 

	import numpy as np

Step 2 — Generate a 5x5 Random Array

	X = np.random.rand(5, 5)  # Generates random numbers between 0 and 1
	print("Original X:\n", X)

Step 3 — Calculate Mean & Standard Deviation

	mean = X.mean()
	std = X.std()
	print("\nMean of X:", mean)
	print("Standard Deviation of X:", std)

Step 4 — Normalize the Array

	X_normalized = (X - mean) / std
	print("\nNormalized X:\n", X_normalized)

Step 5 — Save the Normalized Array

	np.save("X_normalized.npy", X_normalized)



## ** Problem 2: DIVI by 3 **

1st - Define the function

	def d_by3_array(n):

This creates a function named d_by3_array that will collect n squares divisible by 3 and return a 10×10 array (in your code you call it with n = 100).


2nd - Initialize helper variables

	divisible = []   # List to store numbers divisible by 3
	num = 1          # Start checking from 1
	count = 0        # How many valid squares we've found

"divisible" will hold the squares (like 9, 36, 81, ...).
"num" is the integer we will square each loop.
"count" tracks how many valid items we stored so far.


3rd - Loop until we have n numbers

	while count < n:
 	   sq = num ** 2
   		if sq % 3 == 0:
        	divisible.append(sq)
        	count = count + 1
    	num = num + 1

- "sq = num ** 2" computes the square of num (** means power).
- if sq % 3 == 0: checks divisibility by 3 (% is remainder).
- If divisible, append it to divisible and increase count.
- Always increment "num" so we move to the next integer.

Quick math note: a square n**2 is divisible by 3 exactly when n is divisible by 3. So the code finds squares of 3, 6, 9, 12, ... 


4th - Prepare to build the 10×10 array

	array_tBt = []
	index = 0
 
- array_tBt will become the 2D array (list of rows).
- index tracks the position in the divisible list while filling rows and columns.


5th - Fill 10 rows and 10 columns

	for row in range(10):      # 10 rows
    	nemo = []              # start a new row
    	for col in range(10):  # 10 columns in each row
        	nemo.append(divisible[index])
        	index = index + 1
    	array_tBt.append(nemo) # add the completed row to the array


- Outer loop runs 10 times (rows).
- Inner loop runs 10 times (columns per row).
- Each cell gets divisible[index]; then index increments to move through the divisible list.
- array_tBt.append(nemo) adds the finished row.


6th - Return the final 10×10 array

	return array_tBt

- After filling, the function gives back the 2D array.


7th - Call the function and print the result

	result = d_by3_array(100)
	print('A = ')
	for nemo in result:
    	print(nemo)


- result receives the 10×10 array from the function.
- We print a label 'A = ' then print each row (nemo) line by line.

## Example (first two rows you should see)
	A =
	[9, 36, 81, 144, 225, 324, 441, 576, 729, 900]
	[1089, 1296, 1521, 1764, 2025, 2304, 2601, 2916, 3249, 3600]
	...


(These are squares of 3, 6, 9, ... 30 for the first row; then 33, 36, 39, ... 60 for the second, and so on.)

## How to run (step-by-step)
- Put all the code into a file, e.g. divisible_by3_array.py.
- Open a terminal in the folder with that file.
- Run:
- You’ll see the 10×10 matrix printed.

