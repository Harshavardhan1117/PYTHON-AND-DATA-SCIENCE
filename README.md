# PYTHON-AND-DATA-SCIENCE
## PDS ASSIGNMENT

# Q1. Two Sum Problem

def two_sum(nums, target):

    for i in range(len(nums)):
        for j in range(i + 1, len(nums)):
            if nums[i] + nums[j] == target:
                return [i, j]
    print("Q1 Outputs:")
    print(two_sum([2, 7, 11, 15], 9))   # Output: [0, 1]
    print(two_sum([3, 2, 4], 6))        # Output: [1, 2]
    print(two_sum([3, 3], 6))           # Output: [0, 1]

Output:

[0, 1]

[1, 2]

[0, 1]
    


# Q2. Palindrome Number

def is_palindrome(x):

    if x < 0:
        return False
    return str(x) == str(x)[::-1]
    print("\nQ2 Outputs:")
    print(is_palindrome(121))   # Output: True
    print(is_palindrome(-121))  # Output: False
    print(is_palindrome(10))    # Output: False

Output:

True

False

False
    


# Q3. Longest Common Prefix

def longest_common_prefix(strs):

    if not strs:
        return ""
    prefix = strs[0]
    for s in strs[1:]:
        while not s.startswith(prefix):
            prefix = prefix[:-1]
            if prefix == "":
                return ""
    return prefix

    print("\nQ3 Outputs:")
    print(longest_common_prefix(["flower", "flow", "flight"]))  # Output: "fl"
    print(longest_common_prefix(["dog", "racecar", "car"]))     # Output: ""

Output:

fl

""

# Q4. Roman Numerals to Integer

def roman_to_int(s):

    roman = {
        'I': 1, 'V': 5, 'X': 10, 'L': 50,
        'C': 100, 'D': 500, 'M': 1000
    }
    total = 0
    prev_value = 0
    for char in reversed(s):
        value = roman[char]
        if value < prev_value:
            total -= value
        else:
            total += value
        prev_value = value
    return total

    print(roman_to_int("III"))      # Output: 3
    print(roman_to_int("LVIII"))    # Output: 58
    print(roman_to_int("MCMXCIV"))  # Output: 1994

Output:

3

58

1994
    

# Q5. Square Root (without built-in functions)

def my_sqrt(x):

    if x == 0 or x == 1:
        return x
    left, right = 0, x
    ans = 0
    while left <= right:
        mid = (left + right) // 2
        if mid * mid <= x:
            ans = mid
            left = mid + 1
        else:
            right = mid - 1
    return ans

    print("\nQ5 Outputs:")
    print(my_sqrt(4))  # Output: 2
    print(my_sqrt(8))  # Output: 2

Output:

2

2
    
# Q6. Difference Between Python Lists and NumPy ndarrays

    import numpy as np


    print("\nQ6 Outputs:")
    py_list = [1, 2, 3, 4, 5]
    print("Python List:", py_list)
    print("Type:", type(py_list))

    np_array = np.array([1, 2, 3, 4, 5])
    print("\nNumPy ndarray:", np_array)
    print("Type:", type(np_array))

    print("\nList + List:", py_list + py_list)        # Concatenation
    print("Array + Array:", np_array + np_array)      # Element-wise addition

Output:

Python List: [1, 2, 3, 4, 5]

Type: <class 'list'>

NumPy ndarray: [1 2 3 4 5]

Type: <class 'numpy.ndarray'>

List + List: [1, 2, 3, 4, 5, 1, 2, 3, 4, 5]

Array + Array: [ 2  4  6  8 10]
    

# Q7. Creating DataFrames using Pandas

    import pandas as pd

    print("\nQ7 Outputs:")
    data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'City': ['Bangalore', 'Mumbai', 'Delhi']
    }

    df = pd.DataFrame(data)
    print("DataFrame from Dictionary:")
    print(df)

    data_list = [
    ['David', 28, 'Pune'],
    ['Eva', 22, 'Chennai']
    ]
    df2 = pd.DataFrame(data_list, columns=['Name', 'Age', 'City'])
    print("\nDataFrame from List of Lists:")
    print(df2)

Output:

DataFrame from Dictionary:
Name  Age       City

0    Alice   25  Bangalore

1      Bob   30     Mumbai

2  Charlie   35      Delhi

DataFrame from List of Lists:
Name  Age     City

0  David   28     Pune

1    Eva   22  Chennai
