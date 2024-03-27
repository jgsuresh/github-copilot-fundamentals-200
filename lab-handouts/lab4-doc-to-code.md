# Doc to Code with GitHub Copilot

While we are able to generate documentation using GitHub Copilot, it is also possible to generate code _from_ documentation, giving us the upper hand as developers when perhaps a program has already been explained, and now it just needs to be developed. 

### Task 1

1. For the purposes of this exercise, you will be investingating SIR models, as shown in the `SIR_documentation.md` file in the `lab-files` directory. Please take a few moments to read through that documentation now.

2. Select all of the code in `SIR_documentation.md`, Open GitHub Copilot Chat and prompt it to generate a program from the selected documentation

```
Generate a program based on the selected documentation
```

## Task 2

1. Insert the code into a new file named `SIR.cs`. Your code should look similar to the code below:

```
public class SIRModel
{
    private double susceptible;
    private double infected;
    private double recovered;
    private double totalPopulation;
    private double beta;
    private double gamma;

    public SIRModel(double totalPopulation, double initialInfected, double initialRecovered, double beta, double gamma)
    {
        this.totalPopulation = totalPopulation;
        this.infected = initialInfected;
        this.recovered = initialRecovered;
        this.susceptible = totalPopulation - initialInfected - initialRecovered;
        this.beta = beta;
        this.gamma = gamma;
    }

    public void Calculate(double timeStep, int steps)
    {
        for (int i = 0; i < steps; i++)
        {
            double newInfected = timeStep * beta * susceptible * infected / totalPopulation;
            double newRecovered = timeStep * gamma * infected;

            susceptible -= newInfected;
            infected += newInfected - newRecovered;
            recovered += newRecovered;

            Console.WriteLine($"Step {i}: Susceptible = {susceptible}, Infected = {infected}, Recovered = {recovered}");
        }
    }
}

class Program
{
    static void Main(string[] args)
    {
        SIRModel model = new SIRModel(1000, 1, 0, 0.4, 0.1);
        model.Calculate(0.5, 100);
    }
}
```

**In this program, the SIRModel class represents the SIR model. The Calculate method calculates the SIR model over a given number of steps, with each step representing a time interval specified by timeStep. The Main method creates an instance of the SIRModel class and calls the Calculate method to calculate the SIR model. The results are printed to the console at each step.**

2. If your generated program does not contain a `Calculate()` function, reprompt GitHub Copilot to add a calculate method:

```
Add a calculate method to the generated code
```

3. Add the finalized code into the `SIR.cs` file

## Task 3

1. In `SIR.cs`, select all of the code and prompt inline GitHub Copilot Chat (Ctrl+I) to provide a number of code quality improvements:
  a. `Add docstrings to the selected code`
  b. `Add comments to the selected code`

2. Still with the code selected, open the GitHub Copilot Chat window

3. Prompt GitHub Copilot Chat to analyze the code and determine if it can be refactored in any way:

```
Can the code be refactored for simplicity?
```

4. GitHub Copilot will provide a list of suggestions for refactoring, prompt the tool to write the code for a few of them and add the changes into a new file named `refactoredSIR.cs`

5. Save your changes and ensure that all files are saved within the `lab-files` directory

6. Move onto the [next lab task](lab-handouts/lab5-code-translation.md)
