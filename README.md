# Mars ESM Analysis Tool

This Python tool allows you to analyze and compare different scenarios in Mars ESM (Equivalent System Mass) based on the data you provide in an Excel file.

# Mars ESM Equation

The Mars ESM (Equivalent System Mass) is calculated using the following equation:


ESM_{Mars} = \frac{Mass + Volume \cdot V_{eq} + Power \cdot P_{eq} + Cooling \cdot C_{eq} + Crewtime \cdot duration \cdot CT_{eq} + Water \cdot duration \cdot W_{eq}}{Resource \cdot duration \cdot R_{eq} + Medicine \cdot duration \cdot M_{eq} + Nutrients \cdot duration \cdot N_{eq} + Material \cdot duration \cdot M_{eq} + 1}

- $Mass$: Mass of the system (in kg)\\
- $Volume$: Volume of the system (in cubic meters)\\
- $V_{eq}$: Conversion factor for Volume (in kg/m$^3$)\\
- $Power$: Power requirement of the system (in kW$_{electrical})$\\
- $P_{eq}$: Conversion factor for Power (in kg/kW$_{electrical})$\\
- $Cooling$: Cooling requirement of the system (in kW$_{thermal})$\\
- $C_{eq}$: Conversion factor for Cooling (in kg/kW$_{thermal})$\\
- $Crewtime$: Crewtime requirement of the system (in hours/day)\\
- $CT_{eq}$: Conversion factor for Crewtime (in kg/hour)\\
- $Water$: Water requirement of the system (in liters/day)\\
- $W_{eq}$: Conversion factor for Water (in kg/liter)\\
- $Resource$: Resource production of the system (in kg/day)\\
- $R_{eq}$: Conversion factor for Resource (in kg/kg)\\
- $Medicine$: Medicine production of the system (in kg/day)\\
- $Med_{eq}$: Conversion factor for Medicine (in kg/kg)\\
- $Nutrients$: Nutrient production of the system (in kg/day)\\
- $Nut_{eq}$: Conversion factor for Nutrients (in kg/kg)\\
- $Material$: Material production of the system (in kg/day)\\
- $Mat_{eq}$: Conversion factor for Material (in kg/kg)\\
- $Duration$: Duration of operation (in days)\\



## Getting Started

1. **Update your Excel file:** The tool requires an Excel sheet with specific columns, including `Name`, `Mass`, `Volume`, `Power`, `Cooling`, `Crewtime`, `Duration`, `Water`, `Resource`, `Medicine`, `Nutrients`, `Material`, and `Tag`. Each row in the Excel sheet should represent a component of a system with its attributes. Here's an example of the expected data format:

    ```
    Name           Mass    Volume    Power    Cooling    Crewtime    Duration    Water    Resource    Medicine    Nutrients    Material    Tag
    Vessel         100     100       100      100        100         100         100      100         100         0            0           bioreactor
    Plastic polymer100     10        0        0          0           100         0        0           0           0            0           shipping
    Pump           10      1         100      100        100         100         0        0           0           0            0           bioreactor
    ```

    Save the file as `ESM_book.xlsx`.

2. **Run the Python code:** After saving your Excel file in the same directory as your Python script, run the Python code provided. The code will prompt you to enter the scenarios you want to analyze. Enter the scenarios as a comma-separated list (for example, `bioreactor,shipping`).

## What the Tool Does

The tool first reads your Excel file and fills any missing data with zeros. It then creates sub-dataframes for each scenario you've entered, calculating a summary row for each scenario. These summaries include the sum of the numerical columns and the concatenation of non-numerical columns.

The code then generates an interactive plot based on your scenarios, using sliders to adjust the parameters that influence the computation of Mars ESM. The plot represents the Mars ESM values over a range of operation days for each scenario.

## Interacting with the Plot

You can interact with the plot using the sliders provided. Each slider represents a different parameter used in the Mars ESM calculation. By adjusting these sliders, you can see how changes to these parameters affect the Mars ESM over time.

## Customizing the Tool

The tool can be customized to suit your specific needs. You can adjust the sliders' ranges and steps, the figure size, and the attributes in the Excel file. Please ensure that any adjustments you make are consistent throughout the code.

This tool is a powerful way to visually compare different Mars ESM scenarios based on the parameters that matter most to your project. Enjoy exploring your data!
