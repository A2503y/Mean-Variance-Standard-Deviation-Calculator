# Mean, Variance, and Standard Deviation Calculator

This project provides a Python function to calculate the mean, variance, standard deviation, max, min, and sum of a 3x3 matrix.

## Features

- Calculates the following statistics for a 3x3 matrix:
    - Mean (axis 0, axis 1, and flattened)
    - Variance (axis 0, axis 1, and flattened)
    - Standard Deviation (axis 0, axis 1, and flattened)
    - Max (axis 0, axis 1, and flattened)
    - Min (axis 0, axis 1, and flattened)
    - Sum (axis 0, axis 1, and flattened)
- Input must be a list containing nine numbers.
- Returns a dictionary containing the calculated statistics.

## Requirements

- Python 3.x
- NumPy

## Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/mean-variance-standard-deviation-calculator.git
    cd mean-variance-standard-deviation-calculator
    ```
2.  **Install dependencies:**
    ```bash
    pip install numpy
    ```

## Usage

The main component of this project is the `calculate` function, found in `Mean_Variance_Standard_Deviation_Calculator.py`.

```python
import numpy as np

def calculate(input_list):
    if len(input_list) != 9:
        raise ValueError("List must contain nine numbers.")
    # Convert the list into a 3x3 NumPy array
    arr = np.array(input_list).reshape(3, 3)

    # Calculate mean, variance, standard deviation, max, min, and sum
    # along both axes and for the flattened matrix
    calculations = {
        'mean': [arr.mean(axis=0).tolist(), arr.mean(axis=1).tolist(), arr.mean().item()],
        'variance': [arr.var(axis=0).tolist(), arr.var(axis=1).tolist(), arr.var().item()],
        'standard deviation': [arr.std(axis=0).tolist(), arr.std(axis=1).tolist(), arr.std().item()],
        'max': [arr.max(axis=0).tolist(), arr.max(axis=1).tolist(), arr.max().item()],
        'min': [arr.min(axis=0).tolist(), arr.min(axis=1).tolist(), arr.min().item()],
        'sum': [arr.sum(axis=0).tolist(), arr.sum(axis=1).tolist(), arr.sum().item()]
    }
    return calculations

# Example
if __name__ == "__main__":
    numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8]
    try:
        results = calculate(numbers)
        print(results)
    except ValueError as e:
        print(e)

    # Example of invalid input
    # invalid_numbers = [1, 2, 3]
    # try:
    #     results_invalid = calculate(invalid_numbers)
    #     print(results_invalid)
    # except ValueError as e:
    #     print(e)
```

To use the `calculate` function:

1.  Ensure you have `Mean_Variance_Standard_Deviation_Calculator.py` in your project directory.
2.  Import the function into your Python script:
    ```python
    from Mean_Variance_Standard_Deviation_Calculator import calculate
    ```
3.  Call the function with a list of nine numbers:
    ```python
    my_list = [2,6,2,8,4,0,3,5,1]
    statistics = calculate(my_list)
    print(statistics)
    ```

## Running the `Mean_Variance_Standard_Deviation_Calculator.py` script

You can also run the `Mean_Variance_Standard_Deviation_Calculator.py` script directly if it includes an example usage block (like the one shown in the Usage section, guarded by `if __name__ == "__main__":`).

1.  Save the `Mean_Variance_Standard_Deviation_Calculator.py` file.
2.  Run the file from your terminal:
    ```bash
    python Mean_Variance_Standard_Deviation_Calculator.py
    ```
    This will execute the example usage within the script and print the dictionary of calculations.

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate if any exist.

## License

[MIT](https://choosealicense.com/licenses/mit/)
This means you are free to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software. See the LICENSE file for more details (if one is present, typically it would be named `LICENSE` or `LICENSE.md`).
