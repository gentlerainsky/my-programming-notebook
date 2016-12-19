#R note

source: coursera's statistics specialisation course

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

**range of data in a column**
- range(DATA_VARIABLE_NAME$COLUMN_NAME) eg. range(present$year)

**add two column**
- COLUMN_1 + COLUMN_2 eg. arbuthnot$boys + arbuthnot$girls

**print a column**
- DATA_VARIABLE_NAME$COLUMN_NAME eg. arbuthnot$boys

**adding a new variable to a data frame**
- arbuthnot <- arbuthnot %>% mutate(total = boys + girls)

The %>% operator is called the piping operator. Basically, it takes the output of the current line and pipes it into the following line of code.

A note on piping: Note that we can read these three lines of code as the following:

“Take the arbuthnot dataset and pipe it into the mutate function. Using this mutate a new variable called total that is the sum of the variables called boys and girls. Then assign this new resulting dataset to the object called arbuthnot, i.e. overwrite the old arbuthnot dataset with the new one containing the new variable.”

This is essentially equivalent to going through each row and adding up the boys
and girls counts for that year and recording that value in a new column called total.

**structure of data**
- str(DATA_VARIABLE_NAME)

 taking a quick peek at your data frame, and viewing its dimensions and data types is str, which stands for structure.

**Turn numerical data to categorical**
- factor(COLUMN_NAME)

the data frame month is stored as a numerical variable (numbers 1 - 12). Therefore we can force R to treat this variable as categorical, what R calls a factor, variable with factor(month). 
 
**plot some graph using ggplot**

```R
ggplot(data = DATA_VARIABLE_NAME, aes(x = COLUMN_NAME_1, y = COLUMN_NAME_2)) + PLOT_STYLE_FUNC()
```
eg.
```R
ggplot(data = arbuthnot, aes(x = year, y = girls)) + geom_point()
```

The first argument is always the dataset.
Next, we provide the variables from the dataset to be assigned to aesthetic elements of the plot, e.g. the x and the y axes.
Finally, we use another layer, separated by a + to specify the geometric object for the plot. Since we want to scatterplot, we use  geom_point.

*some plot styles*

- geom_point - scatterplot
- geom_line - line graph
- geom_histogram() - histogram

you can use both plot styles by adding together both function ex. geom_point() + geom_line()

**view function documentation**
- ?FUNCTION_NAME eg. ?ggplot

**Package: dplyr**

**filter**
- rdu_flights <- nycflights %>% filter(dest == "RDU")

filter on multiple criteria

- sfo_feb_flights <- nycflights %>% filter(dest == "SFO", month == 2)

**numerical summaries**
- rdu_flights %>% summarise(mean_dd = mean(dep_delay), sd_dd = sd(dep_delay), n = n())

list of summary statistics available `mean`, `median`, `sd`, `var`, `IQR`, `range`, `min`, `max`

**group data before calculation**
- rdu_flights %>% group_by(origin) %>% summarise(mean_dd = mean(dep_delay), sd_dd = sd(dep_delay), n = n())

**arrange the output**
- nycflights %>% group_by(month) %>% summarise(mean_dd = mean(dep_delay)) %>% arrange(desc(mean_dd))

