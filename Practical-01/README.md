# Practical 01 - Revisiting Pandas and NumPy

| | |
|---|---|
| **Submitted By** | Divij Grack |

## 1. Objective

To practise basic data handling with pandas and array operations with NumPy. The practical covers:

- Creating a DataFrame from raw data
- Selecting DataFrame columns and converting them to a NumPy array
- Checking an array's shape, size and number of dimensions
- Performing arithmetic operations on matrices
- Finding a matrix transpose and inverse

## 2. Dataset

The notebook defines a small employee dataset directly in Python; no external data file is needed.

- **Size:** 4 rows x 4 columns (four employees)

| Variable | Meaning |
|---|---|
| Employee_ID | Employee identifier |
| Department | Employee's department |
| Salary | Employee's salary |
| Bonus | Employee's bonus |

## 3. Approach

1. Imported pandas and NumPy.
2. Created a dictionary of employee IDs, departments, salaries and bonuses, then converted it into a pandas DataFrame.
3. Selected the `Salary` and `Bonus` columns and converted them to a NumPy array.
4. Printed the array and checked its shape, size and number of dimensions.
5. Defined two 2 x 2 matrices and used NumPy to calculate their sum, difference and element-wise product.
6. Calculated the transpose and inverse of the first matrix.

## 4. Tools Used

Python 3, Jupyter Notebook, pandas, NumPy

## 5. Results

| Operation | Result |
|---|---|
| Employee DataFrame | 4 rows x 4 columns |
| Salary and bonus array | `[[50000, 5000], [75000, 7000], [80000, 8000], [65000, 6000]]` |
| Array shape, size and dimensions | `(4, 2)`, `8`, `2` |
| A + B | `[[5, 10], [4, 11]]` |
| A - B | `[[3, 4], [0, 1]]` |
| Element-wise A x B | `[[4, 21], [4, 30]]` |
| Transpose of A | `[[4, 2], [7, 6]]` |
| Inverse of A | `[[0.6, -0.7], [-0.2, 0.4]]` |

## 6. Key Takeaways

- A pandas DataFrame stores the employee records in labeled rows and columns, while NumPy represents the selected numeric columns as a two-dimensional array.
- The salary and bonus array has four rows and two columns, eight values in total, and two dimensions.
- NumPy provides concise functions for element-wise matrix arithmetic, transposition and inversion.

## 7. Conclusion

This practical revisited core pandas and NumPy operations: creating a DataFrame, selecting numeric data, inspecting array properties and applying matrix operations. The examples use a small in-notebook employee dataset and two 2 x 2 matrices.
