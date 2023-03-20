# Using AI to aid coding

## Introduction

## Start

### Can we make a barplot in R using AI to generate the code

using [openai](https://chat.openai.com/chat)

we ask it `write a script in R plot a bargraph`.

we then get the following code

```
# Create sample data
x <- c("Apples", "Oranges", "Bananas", "Grapes")
y <- c(20, 15, 10, 25)

# Plot the bar graph
barplot(y, names.arg = x, main = "Fruit Sales", ylab = "Number of Sales")
```
and the follwing explaination:

```
Let me explain the code line by line:

We create a vector x containing the names of fruits, and a vector y containing the number of sales for each fruit.
The barplot() function is used to create the bar graph. The first argument y is the height of the bars. The names.arg argument is used to label each bar with the corresponding fruit name. The main argument specifies the main title of the graph, and the ylab argument specifies the label for the y-axis.
When you run this code, you should see a bar graph with four bars, labeled "Apples", "Oranges", "Bananas", and "Grapes". The height of each bar corresponds to the number of sales for the corresponding fruit.

```
The code produces the following 


![](pics/openAI_barplot1.png)

This is OK, but lets say we have our own data we wish to plot.

we could ask the AI:

`write a script in R to plot a barplot from existing data`

and get the following:

```
# Load the data
data <- read.csv("sales_data.csv")

# Plot the barplot
barplot(data$Sales, names.arg = data$Product, 
        main = "Sales by Product", ylab = "Number of Sales", xlab = "Product Name")
```



With the explaination:

```
Here's what each line of the code does:

We load the data from a CSV file named "sales_data.csv" into a data frame named data. You'll need to replace "sales_data.csv" with the name of your own file, or the  file path if it's in a different directory.

We use the barplot() function to create a barplot of the sales data. The first argument data$Sales specifies the height of each bar, which we're pulling from the "Sales" column of our data frame. The names.arg argument is used to label each bar with the corresponding product name, which we're pulling from the "Product" column of our data frame. The main argument specifies the main title of the graph, and the ylab and xlab arguments specify the labels for the y-axis and x-axis, respectively.

When you run this code, you should see a barplot of the sales data, with each bar labeled with the corresponding product name. The height of each bar corresponds to the sales value for the corresponding product.

```

We will of course, have to change the code to make the script work with our existing data `single-filtered.csv` and the different column names the data has.

The code then becomes:

```

# Load the data
#data <- read.csv("sales_data.csv")
data <- read.csv("single-filtered.csv")

# Plot the barplot
# barplot(data$Sales, names.arg = data$Product, 
#         main = "Sales by Product", ylab = "Number of Sales", xlab = "Product Name")
barplot(data$strain, names.arg = data$snp_type, 
        main = "Sales by Product", ylab = "Number of Sales", xlab = "Product Name")


```

which produces a plot like this:

![](pics/openAI_barplot2.png)


