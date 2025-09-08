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
    
    1. 1. NumPy Array Normalization
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
