# Test Driven Development with GitHub Copilot

Test-driven development (TDD) with GitHub Copilot represents a powerful synergy of software development practices and cutting-edge AI assistance. With TDD, developers follow a process of writing tests before implementing their code. It actively assists in crafting test cases, generating test templates, and suggesting test scenarios based on the code being written

## Task 1

1. Prompt Copilot Chat to ask about the directory structure and naming conventions for testing in Python:

```
What is the directory structure and naming conventions for testing in Python?
```

2. _If you are using VS Code, prompt Copilot Chat to create a new Python project:_

```
@workspace /new Create a new Python project with a test directory and a test file named test_installments.py and a main directory with a file named equated_monthly_installments.py
```

3. _If you are using IntelliJ IDEA, create a new Python file in the lab-files directory named `test_installments.py`_

2. Open GitHub Copilot Chat and prompt it to generate test cases for a program that calculates amortization amount per month

**Note, this program has not yet been written**

```
Generate 5 test cases for a Python program that calculates the amoritzation amount per month, given: 
- Principal borrowed
- Rate of interest per annum
- Years to repay the loan
```

3. Add the code from step 1 into your new testing file, ensure this file is named `test_installments.py`

## Task 2

1. If you are using VSCode, move into your `equated_monthly_installments.py` file, if you are using IntelliJ IDEA, create a new Python file named `equated_monthly_installments.py`

2. Open GitHub Copilot Chat

3. Select the test cases in `test_installments.py` and prompt Copilot Chat to generate a program that will pass the tests, asking it to think step-by-step

```
Generate a program that will pass the selected tests, think step-by-step
```
4. Copy the code from Copilot Chat into your `equated_monthly_installments.py` file

5. Use inline GitHub Copilot to make code quality improvements as needed (e.g. variable names, comments, etc.)

## Task 3

1. Review Copilot's rationale for the code, and add its suggestions into your `equated_monthly_installments.py` file. Your code may look similar to the program below: 

```
def equated_monthly_installments(
    principal: float, rate_per_annum: float, years_to_repay: int
) -> float:
    if principal <= 0:
        raise Exception("Principal borrowed must be > 0")
    if rate_per_annum < 0:
        raise Exception("Rate of interest must be >= 0")
    if years_to_repay <= 0 or not isinstance(years_to_repay, int):
        raise Exception("Years to repay must be an integer > 0")

    # Yearly rate is divided by 12 to get monthly rate
    rate_per_month = rate_per_annum / 12

    # Years to repay is multiplied by 12 to get number of payments as payment is monthly
    number_of_payments = years_to_repay * 12

    return (
        principal
        * rate_per_month
        * (1 + rate_per_month) ** number_of_payments
        / ((1 + rate_per_month) ** number_of_payments - 1)
    )

```

## Task 4

1. If your code does not contain a docstring, prompt inline GitHub Copilot Chat (Ctrl+I) to generate one: `Generate a docstring for the above code`

2. Add the docstring into your new file

3. Run the tests in `test_installments.py` to ensure that your program passes all the tests

    #### Using the VS Code Terminal

    1. Open the terminal in VS Code by pressing `Ctrl + `` 
    2. Run the command `python -m unittest test_installments.py`

    #### Using the IntelliJ IDEA Terminal

    1. Open the terminal in IntelliJ IDEA by pressing `Alt + F12`
    2. Run the command `python -m unittest test_installments.py`

## Task 5

1. Save your code and ensure that files are being saved into the `lab-files` directory

2. Move onto the [next lab task](lab-handouts/lab3-generating-documentation.md)
