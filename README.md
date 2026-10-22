# Student Utilities

A simple Python project that calculates a student's average marks, checks passing status, and assigns a grade.

## Features

- Calculate the average of marks.
- Check whether a student has passed.
- Assign grades based on the average.

## Functions

### 1. `calculate_average(marks)`

Calculates the average by adding all marks and dividing the total by the number of marks.

Example:

```python
calculate_average([80, 90, 100])
# Output: 90.0
```

### 2. `is_passing(mark)`

Checks whether a mark is greater than or equal to `PASS_MARK`, which is set to 40.

```python
is_passing(40)  # True
is_passing(39)  # False
is_passing(75)  # True
```

### 3. `get_grade(average)`

Assigns a grade according to the student's average.

| Average | Grade |
|---|---|
| 90 and above | Distinction |
| 60 to below 90 | First |
| 45 to below 60 | Second |
| Below 45 | Fail |

Example:

```python
get_grade(95)  # "Distinction"
get_grade(65)  # "First"
get_grade(50)  # "Second"
```

## Usage Example

```python
from student_utils import calculate_average, is_passing, get_grade

marks = [80, 90, 100]

average = calculate_average(marks)
print("Average:", average)
print("Passing:", is_passing(average))
print("Grade:", get_grade(average))
```

Output:

```text
Average: 90.0
Passing: True
Grade: Distinction
```

## Run Tests

Run the following command in your terminal:

```bash
python test_student_utils.py
```

The test file contains nine tests for average calculation, passing status, and grade assignment. After fixing the identified bugs, all nine tests should pass.


## Project Structure

```text
.
├── student_utils.py
├── test_student_utils.py
├── README.md
└── audit.md
```

## Requirements

- Python 3
- No external libraries required.

## Conclusion

This project demonstrates Python functions, arithmetic operations, conditional statements, and unit testing.