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

** Problem 1: NumPy Array Normalization **

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

** Problem 1: NumPy Array Normalization **

*Step 1 — Define the Function*
We’ll create a function called *d_by3_array* that does all the work.

def d_by3_array(n):
    divisible = []   # This list will store the perfect squares
    num = 1         # Start counting from 1

    def d_by3_array(n):
    divisible = []   # This list will store the perfect squares
    num = 1         # Start counting from 1

    # Keep going until we have 'n' numbers
    while len(divisible) < n:
        sq = num ** 2       # Square the current number
        if sq % 3 == 0:     # Check if the square is divisible by 3
            divisible.append(sq)  # If yes, add it to the list
        num += 1            # Go to the next number

*Beginner Tip:*
num ** 2 means num ^ num.
sq % 3 == 0 checks if the number is divisible by 3.

*Step 2 — Make a 10x10 Array*
    # Turn the list into a 10x10 grid
    array_2D = []       # Final table
    index = 0

    for row in range(10):          # Loop 10 times for 10 rows
        current_row = []           # Make an empty row first
        for col in range(10):      # Add 10 numbers per row
            current_row.append(divisible[index])
            index += 1             # Move to the next number
        array_2D.append(current_row)  # Add the completed row to the table

    return array_2D
*Beginner Tip:*
Think of rows as horizontal lines in the table.
We use two loops: one for rows, one for columns.


