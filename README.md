# Push Swap Tester Script

This repository contains a script to test the `push_swap` program with various permutations and random sets of numbers. It checks the number of moves and validates the results using the `checker` program. Additionally, it verifies memory leaks using `valgrind`. The script outputs color-coded results for easy readability.

## Prerequisites

- Python 3
- `push_swap` executable
- `checker` executable
- `valgrind` installed

## Usage

1. **Clone the repository**:
    ```bash
    git clone https://github.com/nerovanity/Push_Swap_42Tester.git
    cd push_swap_tester
    ```

2. **Ensure the `push_swap` and `checker` executables are in the same directory as the script or update the paths in the script accordingly.**

3. **Make the script executable and run it**:
    ```bash
    chmod +x test.sh
    ./test.sh
    ```

4. **Select the number of elements to test** (1-Custom number, 3, 4, 5, 100, 500) when prompted.

## Description

The script performs the following steps:

1. **Generate Numbers**: Depending on the user's input, it generates permutations for small sets (3, 4, 5) or random numbers for larger sets (between 6 and 100, 500).
2. **Run Tests**: For small sets, it runs a single test. For larger sets, it runs three tests with different random numbers.
3. **Check Results**: It runs the `push_swap` and `checker` programs, counts the number of moves, and verifies the results.
4. **Memory Leak Check**: It uses `valgrind` to check for memory leaks.
5. **Output**: It outputs the results in color-coded format:
    - Green for "OK" and "No Leaks"
    - Red for "KO" and "LEAKS"
6. **Move Limits**: It checks if the number of moves is within specified limits:
    - 3 numbers: less than or equal to 3 moves
    - 5 numbers: less than 12 moves
    - 100 numbers: less than 700 moves
    - 500 numbers: less than 5500 moves
7. **Final Result**: It outputs "All tests passed" in green if all tests pass, otherwise it outputs "Some tests failed" in red.

## Example Output
```diff
Select the number of elements to test (1-Custom number, 3, 4, 5, 100, 500):
100
Select the number of tests:
3
Test 1 for 100 numbers
Testing permutation: 62 21 71 15 99 74 32 68 75 25 83 34 92 76 2 20 6 29 89 5 9 63 61 45 85 64 50 67 52 55 42 7 14 93 84 4 22 16 49 40 11 59 94 53 24 26 47 97 69 79 57 12 82 38 80 33 28 88 72 39 17 78 70 18 90 13 96 54 48 95 41 51 10 43 87 66 58 81 27 98 1 23 3 37 35 30 36 77 8 86 44 31 91 65 56 60 73 19 100 46
Permutation: 62 21 71 15 99 74 32 68 75 25 83 34 92 76 2 20 6 29 89 5 9 63 61 45 85 64 50 67 52 55 42 7 14 93 84 4 22 16 49 40 11 59 94 53 24 26 47 97 69 79 57 12 82 38 80 33 28 88 72 39 17 78 70 18 90 13 96 54 48 95 41 51 10 43 87 66 58 81 27 98 1 23 3 37 35 30 36 77 8 86 44 31 91 65 56 60 73 19 100 46 - Moves: 559 - OK
No Leaks
Test 2 for 100 numbers
Testing permutation: 19 32 97 29 8 17 20 96 100 51 25 15 50 92 11 68 63 88 94 38 54 7 60 55 71 16 2 6 93 81 99 69 28 41 79 23 90 58 18 66 26 98 72 3 52 30 78 44 40 22 47 35 59 95 80 10 73 5 27 12 84 9 57 13 34 65 82 24 36 67 76 14 49 61 39 53 86 48 43 1 74 45 46 4 37 42 21 70 89 31 77 85 62 87 56 83 33 64 75 91
Permutation: 19 32 97 29 8 17 20 96 100 51 25 15 50 92 11 68 63 88 94 38 54 7 60 55 71 16 2 6 93 81 99 69 28 41 79 23 90 58 18 66 26 98 72 3 52 30 78 44 40 22 47 35 59 95 80 10 73 5 27 12 84 9 57 13 34 65 82 24 36 67 76 14 49 61 39 53 86 48 43 1 74 45 46 4 37 42 21 70 89 31 77 85 62 87 56 83 33 64 75 91 - Moves: 564 - OK
No Leaks
Test 3 for 100 numbers
Testing permutation: 64 34 50 92 78 46 52 53 48 35 47 5 77 87 54 32 43 1 10 68 11 3 25 79 81 38 15 37 70 44 39 62 56 73 57 51 26 96 99 23 21 98 31 40 76 30 58 16 45 88 75 66 18 2 8 90 7 27 71 65 60 94 9 17 97 84 67 13 55 6 85 83 82 72 4 74 49 95 22 80 86 63 24 59 42 36 20 91 33 100 41 29 93 12 19 14 61 89 28 69
Permutation: 64 34 50 92 78 46 52 53 48 35 47 5 77 87 54 32 43 1 10 68 11 3 25 79 81 38 15 37 70 44 39 62 56 73 57 51 26 96 99 23 21 98 31 40 76 30 58 16 45 88 75 66 18 2 8 90 7 27 71 65 60 94 9 17 97 84 67 13 55 6 85 83 82 72 4 74 49 95 22 80 86 63 24 59 42 36 20 91 33 100 41 29 93 12 19 14 61 89 28 69 - Moves: 592 - OK
No Leaks
All tests passed
```
## Notes

- Ensure that the `push_swap` and `checker` executables are correctly implemented and accessible in the script directory.
- The move limits are based on typical constraints for the `push_swap` project and may need adjustment based on specific requirements.