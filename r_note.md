Basic Library
=============

- dplyr: for data wrangling
- ggplot2: for data visualization

Basic command
-------------

**package installation**
- install.packages
- install_github

**load package**
- library(LIBRARY_NAME) eg. library(dplyr)

**load data**
- data(DATA_FILE) eg. data(arbuthnot)

**show data**
- DATA_VARIABLE_NAME eg. arbuthnot

**data dimension**
- dim(DATA_VARIABLE_NAME) eg. dim(arbuthnot)

**column names**
- names(DATA_VARIABLE_NAME) eg. names(arbuthnot)

**print a column**
- DATA_VARIABLE_NAME$COLUMN_NAME eg. arbuthnot$boys

**plot some graph using ggplot**

```R
ggplot(data = arbuthnot, aes(x = year, y = girls)) +
  geom_point()
```

The first argument is always the dataset.
Next, we provide thevariables from the dataset to be assigned to aesthetic elements of the plot, e.g. the x and the y axes.
Finally, we use another layer, separated by a + to specify the geometric object for the plot. Since we want to scatterplot, we use  geom_point.
