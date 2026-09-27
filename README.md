# Python--Lab--Assignment--4


# =====================================================================
# METHOD 1: Matrix Addition Using Pure Python Lists
# =====================================================================
print("--- Matrix Addition Using Python Lists ---")

# Define matrix dimensions
rows = int(input("Enter the number of rows: "))
cols = int(input("Enter the number of columns: "))

# Initialize and input elements for Matrix A
print("\nEnter elements for Matrix A:")
matrixA = []
for i in range(rows):
    row = [int(x) for x in input(f"Enter row {i+1} elements separated by space: ").split()]
    matrixA.append(row)

# Initialize and input elements for Matrix B
print("\nEnter elements for Matrix B:")
matrixB = []
for i in range(rows):
    row = [int(x) for x in input(f"Enter row {i+1} elements separated by space: ").split()]
    matrixB.append(row)

# Initialize Result Matrix with zeros
result_list = [[0 for _ in range(cols)] for _ in range(rows)]

# Perform Element-wise Matrix Addition
for i in range(rows):
    for j in range(cols):
        result_list[i][j] = matrixA[i][j] + matrixB[i][j]

# Display Output
print("\nResultant Matrix (Using Lists):")
for row in result_list:
    print(row)


# =====================================================================
# METHOD 2: Matrix Addition Using NumPy Arrays
# =====================================================================
import numpy as np

print("\n--- Matrix Addition Using NumPy Arrays ---")

# Convert previous lists directly into NumPy arrays
arrayA = np.array(matrixA)
arrayB = np.array(matrixB)

# NumPy performs element-wise addition natively (Vectorization)
result_numpy = arrayA + arrayB

print("\nMatrix A (NumPy Array):\n", arrayA)
print("Matrix B (NumPy Array):\n", arrayB)
print("\nResultant Matrix (Using NumPy):\n", result_numpy)
