# Generating Documentation with GitHub Copilot

`diophantine_equation.py` contains code that attempts to solve the diphantine_equation. Use this file to demonstrate the capabilities of GitHub Copilot to explain code and create documentation for an existing program

## Task 1

1. Open `diophantine_equation.py` in IDE window

2. Select all of the code in `diophantine_equation.py` and prompt GitHub Copilot to explain the code

```
/explain explain the code in 3 sentences
```
3. Review the explanation. It should be similar to the following: 

**This Python script contains functions to solve Diophantine equations, which are equations where the variables are integers. The diophantine function finds one solution using the Extended Euclidean Algorithm, implemented in the extended_gcd function. The diophantine_all_soln function uses the solution from diophantine to generate multiple solutions, based on a theorem about Diophantine equations.**

4. Open the GitHub Copilot Chat window and chain prompts to generate documentation for the diophantine_equation Python program
  a. Ask GitHub Copilot to answer questions about documentation --> `What are the best practices for markdown documentation?`
  
  b. With the code in `diophantine_equation.py` still selected, create documentation for the diophantine_equation Python program --> `Given the markdown best practices, generate markdown documentation for the selected code`
  
  c. Add the documentation into a new file named `diophantine_documentation.md`

## Task 2

1. Save the new files in the `lab-files` directory 

## Task 3 - Your Turn!

1. Take some time to write your own program, or copy over a file that you have been working on in your personal time

2. Save the file, and keep it open in your workspace, and select the code within the file

3. Prompt GitHub Copilot Chat to explain the program and generate documentation for the file

```
Create documentation for the given code. Including the functions and how to run the program
```

4. Add the generated documentation into a new file named `my_documentation.md`

5. Prompt GitHub Copilot to make corrections as needed

6. Save the new files in the `lab-files` directory

7. Move onto the [next lab task](lab-handouts/lab4-doc-to-code.md)