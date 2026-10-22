# Code Audit — Student Utilities

## 1. Overview

The `student_utils.py` file contains three functions for handling student marks:

- `calculate_average(marks)` — calculates the average of marks.
- `is_passing(mark)` — checks whether a mark meets the passing threshold.
- `get_grade(average)` — assigns a grade based on the average.

The code is tested using `test_student_utils.py` and Python's built-in `unittest` framework.

## 2. Code Review

### `calculate_average(marks)`

**Purpose:** Calculates the average of a list of marks.

**Review:** The function should add all the marks and divide the total by the number of elements in the list.

**Edge case:** An empty list causes a division-by-zero error unless it is handled explicitly.

**Recommendation:** Validate that the list is not empty before calculating the average.

### `is_passing(mark)`

**Purpose:** Checks whether a student has passed.

**Review:** The function uses the `PASS_MARK` constant, set to `40`, as the passing threshold.

**Edge case:** A mark exactly equal to `40` must return `True`.

**Recommendation:** Use an inclusive comparison (`>=`) so that the passing boundary is handled correctly.

### `get_grade(average)`

**Purpose:** Assigns a grade based on the student's average.

**Review:** Grade conditions must be checked from the highest threshold to the lowest.

**Edge case:** An average of `95` must return `Distinction`, not `First`.

**Recommendation:** Check the `90` threshold before the `60` and `45` thresholds.

## 3. Test Coverage

The test file contains nine test cases covering:

- Average calculation for three marks.
- Average calculation for a single mark.
- Average calculation for two marks.
- Passing at the threshold of `40`.
- Failing below the threshold.
- Passing above the threshold.
- Distinction grade.
- First grade.
- Second grade.

**Additional tests recommended:**
- Empty marks list.
- Average below `45`, which should return `Fail`.
- Average exactly at `45`, `60`, and `90`.
- Invalid input types, if input validation is required.

## 4. Correctness and Maintainability

- Keep the utility functions small and focused.
- Use clear function and variable names.
- Keep the test cases separate from the implementation.
- Avoid changing expected test results merely to make incorrect code pass.
- Add input validation where appropriate.

## 5. How to Run the Tests

Run the following command from the project directory:

```bash
python test_student_utils.py
```

The expected result after the identified bugs are fixed is that all nine tests pass.

## 6. Conclusion

The student utilities provide basic functionality for calculating averages, checking passing marks, and assigning grades. The main areas to verify are correct average calculation, inclusive passing-threshold handling, and grade-condition ordering.

The existing tests cover the principal requirements, while additional boundary and invalid-input tests would improve coverage.

**Audit status:** Review prepared. The final implementation should be tested before the code is considered fully verified.