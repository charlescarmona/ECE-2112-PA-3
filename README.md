# ECE-2112-PA-3

**Made by: Charles John M. Carmona | 2ECE-B**

The content of this repository contains Experiment 3 for the course "Advanced Computer Programming and Algorithms" this S.Y. 2026-2027. This experiment focuses on Python Data Analysis using Pandas, particularly loading datasets, selecting rows and columns, and filtering specific data from a DataFrame.

# **A. POSITIONAL AND LABEL-BASED SLICING**

This problem loads the cars.csv dataset into a Pandas DataFrame and displays its shape and column names. It also selects rows 6 to 10 using positional slicing and displays only the specified columns.

The functions used for this are the following:

- `pd.read_csv('cars.csv')` - Loads the CSV file into a Pandas DataFrame.
- `cars.shape` - Returns the number of rows and columns in the dataset.
- `cars.columns.tolist()` - Displays the complete list of column names.
- `cars.iloc[5:10]` - Selects rows 6 through 10 using positional indexing.
- `[['Model', 'mpg', 'cyl', 'hp', 'gear']]` - Selects only the specified columns using their labels.

```Python
import pandas as pd

cars = pd.read_csv('cars.csv')
cars

#Part A.1

#Display the shape of the dataset
print("Dataset Shape:", cars.shape)
#Display the complete list of column names
print("Column Names:", cars.columns.tolist())

#Part A.2

#include only rows from 6 - 10
cars_6_to_10 = cars.iloc[5:10]

cars_6_to_10

#Part A.3

#include only specific categories
Selected_cars = cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]
Selected_cars
```

# **B. MODEL LOOKUP**

This problem uses Boolean indexing to locate specific car models from the dataset without using their row numbers. It first displays the complete information for the Toyota Corolla and then displays only the Model, mpg, hp, and wt columns for the Pontiac Firebird.

The functions and methods used in this problem are the following:

- `cars['Model'] == 'Toyota Corolla'` - Creates a Boolean condition that finds the Toyota Corolla.
- `cars[cars['Model'] == 'Toyota Corolla']` - Returns the complete row of the Toyota Corolla.
- `pontiac_columns` - Stores the column names that need to be displayed for the Pontiac Firebird.
- `cars['Model'] == 'Pontiac Firebird'` - Creates a Boolean condition that finds the Pontiac Firebird.
- `[pontiac_columns]` - Displays only the specified columns for the selected model.

```python
#Part B.1

#Find the model "toyota"
toyota = cars[cars['Model'] == 'Toyota Corolla']
toyota

#Part B.2

#Obtains only columns specified
pontiac_columns = ['Model', 'mpg', 'hp', 'wt']
pontiac = cars[cars['Model'] == 'Pontiac Firebird'][pontiac_columns]

pontiac
```

# **C. MULTI-MODEL SUBSETTING**

This problem creates a new DataFrame containing only three specified car models: Datsun 710, Lotus Europa, and Ferrari Dino. It also retains only the Model, mpg, cyl, hp, and gear columns. The final shape of the DataFrame is checked to make sure that it contains exactly three rows and five columns.

The functions and methods used in this problem are the following:

- `models` - Stores the three car models that need to be selected.
- `models_columns` - Stores the five columns that need to be displayed.
- `cars['Model'].isin(models)` - Checks the Model column and selects rows that match any of the models in the list.
- `[models_columns]` - Retains only the specified columns.
- `Selected_cars.shape` - Displays the number of rows and columns in the final DataFrame.
- `assert Selected_cars.shape == (3, 5)` - Checks that the resulting DataFrame contains exactly three rows and five columns.

```Python
#Obtains the models specified
models = ['Datsun 710', 'Lotus Europa', 'Ferrari Dino']
models_columns = ['Model', 'mpg', 'cyl', 'hp', 'gear']

#Creates a subset selected_cars with the specified models and columns
Selected_cars = cars[cars['Model'].isin(models)][models_columns]
Selected_cars

#Displays the shape of selected_cars
print("Shape of the selected_cars:", Selected_cars.shape)

#The dataframe must contain exactly 3 rows and 5 columns
assert Selected_cars.shape == (3, 5)
```

I APPRECIATE FOR TAKING THE TIME TO READ THIS

Click the link below to see the full main Python program:

https://github.com/charlescarmona/ECE-2112-PA-3/blob/main/CARMONA_2ECE_B_PA3.ipynb

# **Readme File Version History:**

September 10, 2026 - initial Readme Content uploaded

September 10, 2026 - final Readme Content uploaded
