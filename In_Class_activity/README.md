# In-Class Activity

This repository contains Python exercises and pytest examples from the Monday VU in-class activities.

## Requirements

- Python 3.8 or newer
- `pytest`

Install pytest if needed:

```powershell
python -m pip install pytest
```

## Running the tests

Run the complete test suite from this folder:

```powershell
python -m pytest
```

Run one activity at a time:

```powershell
python -m pytest .\Assertions
python -m pytest .\Bank
python -m pytest .\Grade
python -m pytest ".\Positive&Negative"
python -m pytest .\Roman
```

## Activities

### `Assertions`

Basic pytest assertions for common Python collections and floating-point values.

- `test_collections.py` checks list, dictionary, and set comparisons.
- `test_floats.py` demonstrates `pytest.approx` for floating-point precision.

### `Bank`

Introduces a `BankAccount` class in `bank.py`.

- `deposit(amount)` adds a positive amount and returns the new balance.
- `withdraw(amount)` subtracts an amount when sufficient funds are available.
- Invalid deposits and insufficient funds raise `ValueError`.
- `test_dependent.py` shows tests that use shared state.
- `test_independent.py` shows tests that create their own account state.
- `test_bank.py` checks that a deposit increases the balance.

### `Grade`

`grade.py` provides `letter_grade(score)`, which converts a score from 0 to 100 into a letter grade:

| Score | Grade |
| --- | --- |
| 80-100 | A |
| 70-79 | B |
| 60-69 | C |
| 0-59 | F |

Scores outside the range 0-100 raise `ValueError`.

### `Positive&Negative`

`validators.py` contains input validators:

- `validate_email(email)` returns `True` for a valid email format and raises `ValueError` otherwise.
- `validate_age(age)` returns `True` for an integer age from 0 to 150.
- A non-integer age raises `TypeError`; an age outside the range raises `ValueError`.

The two test files cover accepted values and rejected values.

### `Roman`

`roman.py` converts between Roman numerals and integers:

- `roman_to_integer(roman)` accepts standard Roman numerals from 1 to 3999, including lowercase input.
- `integer_to_roman(number)` converts an integer to its Roman numeral representation.
- Invalid characters, repetition, subtraction, ordering, and range errors raise `ValueError` when parsing Roman numerals.

The module can also be run interactively:

```powershell
python .\Roman\roman.py
```

## Project structure

```text
In_Class_activity/
|-- Assertions/
|   |-- test_collections.py
|   `-- test_floats.py
|-- Bank/
|   |-- bank.py
|   |-- test_bank.py
|   |-- test_dependent.py
|   `-- test_independent.py
|-- Grade/
|   |-- grade.py
|   `-- test_grade.py
|-- Positive&Negative/
|   |-- validators.py
|   |-- test_positivevalidators.py
|   `-- test_negativevalidators.py
|-- Roman/
|   |-- roman.py
|   `-- test_roman.py
`-- README.md
```