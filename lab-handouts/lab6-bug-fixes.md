# Fixing Bugs with GitHub Copilot

We are able to use GitHub Copilot to identify bugs within code, and help us to solve an bug-related issues. For the purposes of this exercise, you will be investigating a bug in the code in the `MotionTracking.java` file in the `lab-files` directory. This Java code is an Android activity for a motion tracking application using Google's Project Tango. The code uses the Tango service to track the device's motion and render it using the Rajawali3D engine. The Tango service provides pose data (the device's position and orientation), which can be used to create motion tracking applications.

## Task 1

1. Read through the program in `MotionTracking.java` and see if you can determine the bugs that are currently evident: 

  - the `mConfig` variable is used but not declared
  - the `initializeTango() method is missing a semi-colon at the end`
  - the `onPause()` method is overridden but it doesn't do anything
  - the `disconnectTango` meothod is defined but never called

## Task 2

1. Select the code in `MotionTracking.java` into GitHub Copilot Chat and prompt it to determine the bugs in the code

```
List the bugs/issues that are in the selected code
```
2. GitHub Copilot will provide a list of the bugs in the code. Review the list and determine if the bugs you identified in Task 1 are present in the list. 

**Note: GitHub Copilot most likely will not be able to identify _all_ of the bugs that are identified in Task 1. Additionally, GitHub Copilot may identify bugs that were _not_ listed in Task 1**

**Note: It is possible that GitHub Copilot will identify solutions to the issues that it identified, if that is the case, you can skip step 3**

3. Given the list of bugs provided by GitHub Copilot, determine the best ways to fix the issues, by prompting GitHub Copilot for a solution: 
  - `How can I solve the problem that the mConfig variable is used but not declared? Do not provide a code solution, just a description of how to fix the issue.`
  - `How can I solve the problem that the initializeTango() method is missing a semi-colon at the end? Do not provide a code solution, just a description of how to fix the issue.`
  - `How can I solve the problem that the onPause() method is overridden but it doesn't do anything? Do not provide a code solution, just a description of how to fix the issue.`

4. Review the suggestions provided by GitHub Copilot and determine if they are appropriate solutions to the bugs identified in Task 1

## Task 3

1. Prompt Copilot to fix the bugs in the code using inline GitHub Copilot Chat

2. Open `MotionTracking.java`, select all of the code in the file 

3. Open inline Copilot Chat by pressing **Ctrl + I**

4. Prompt Copilot to fix the bugs in the code task-by-task, with the suggestions provided by GitHub Copilot

  - `Stop the Tango service in the program using the disconnectTango() method`
  - `Define the mConfig variable in the class`
  - `Add a semi-colon to initializeTango()`
  - `Store the Tango object in a class field`

5. Accept each of the suggestions given, ensuring that they address all of the bugs mentioned above

6. Continue to prompt GitHub Copilot to fix any other bugs that were identified but _not_ listed in Task 1

## Task 4

1. Once all of the fixes have been made, highlight all of the code in `MotionTracking.java` and prompt GitHub Copilot to refactor the code

```
Refactor the selected code
```

2. Accept the changes suggested by GitHub Copilot

3. Still with the code selected, prompt GitHub Copilot to format the code

```
Add docstrings and comments to the selected code
```

4. Accept the changes suggested by GitHub Copilot

5. Save your changes, ensuring that all of them were made in the `MotionTracking.java` file 
