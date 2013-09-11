# Data Wrangling & Presentation in R

## Introduction to R and Markdown

### Before we start
- Install R version 3.0.0 or higher from [CRAN](http://cran.stat.sfu.ca)
- Install R Studio from [rstudio.org](http://www.rstudio.com/ide/download/desktop)


% Data Wrangling & Presentation in R
%  Franz Simon, Sean Anderson, Alex Chubaty, & Corey Phillis
% Fall 2013

---------------------

## ![Rlogo](images/Rlogo.png)

### Course Instructors

- Alex Chubaty **B7250** [achubaty@sfu.ca](mailto:achubaty@sfu.ca)
- Corey Phillis **B6226** [cphillis@sfu.ca](mailto:cphillis@sfu.ca)
- Franz Simon **B7250** [fsimon@sfu.ca](mailto:fsimon@sfu.ca)
- Sean Anderson **B6226** [scanders@sfu.ca](mailto:scanders@sfu.ca)

---------------------

# Before we start

- Install R version 3.0.0 or higher from [CRAN](http://cran.stat.sfu.ca)
- Install R Studio from [rstudio.org](http://www.rstudio.com/ide/download/desktop)

---------------------

# Intro to R

---------------------

## The purpose

The purpose of these companion notes is to act as a supplement to lecture 1 of Data Wrangling and Visualization in R. Therefore, these notes will cover three things
1. Basics of good programming practisces
2. Introduction to basic R syntax
3. Introduction to functions that allow you to analyze your data.

At most points these notes will mention common pitfalls and good techniques for working with your data. As you will soon discover there are a million ways to skin a cat; however using a knife is more effective than a photo copier.

---------------------

## What is R?

R is a free software environment for statistical computing and graphics. To see more details see:

[www.r-project.org](http://www.r-project.org)
> free software environment for statistical computing and graphics

Cross-platform (Windows, OSX, Linux)

---------------------

## Why use R?

A more interesting question is "Why use R?" There are several reasons: 

1. Customization
  -  R allows you more control over graphing and statistics than most GUI platforms like JMP.
2. Complexity
  -  R is open source and is supported by a large community. This means that new statistcal techniques when created are quicker to be implented than using SAS since you don't have to wait for a new release of your software 
3. It's *free*
  - This is one of its biggest selling points. As graduate students you are two things: poor and transient. Which means that unless your supervisor has paid a lot of money for a license you will not be able to afford buying proprietary software. The more important thing is you will only be at graduate school for 2-6 years. This means that after you leave university you will no longer be able to work on your statistics anymore if you use a proprietary product.

---------------------

## Using R

- R is a command line tool
    - commands can be entered one line at a time
For example if you open up R console and type 
```{r} 2 + 2 
```
and then press enter you should get a line saying `r 2+2`

Your code will have been executed. 
  - pressing `⇧` in the R terminal will recall the previous command
 
Entering things in line by line is usually inefficent and does not take advantage of one of the big pros of R which is reproducibility. Reprocuibility allows you to perform the same action again in the exact same way. This allows you to run the same analysis on different data, or be able to address reviewer mistakes quicker because you will have saved the commands saying exactly what it is you have done. 

- You can instead execute code by writing a script and executing the script. 

This approach has the advantage of reproduciblity. Also it allows for you to make far bigger and more complex programs since you do not have to re-enter in each command. To do this you will need a code editor. We will be using R-Studio for this course.

---------------------

## Introduction to R-Studio

When you open R studio you will notice four windows. Today you will only focus on the two on the right. The top one is the editor and the bottom window is the R-Console that you used previously.

Now you can create a new R script by typing `Ctrl + Shift + N` or going to the File tab and clicking on new R script.

You will notice that this script works exactly like notepad. You can write and delete text:
For example type 
```{r}
2+2
```
again and press enter. Nothing will happen. In order to actually run your code highlight `2 + 2` and press `Ctrl + Enter`. You will see in the bottom right panel that your code will have executed.

We have now learned how to run a script in R. A whole new world has been opened to you! And it is a dazzling place to be.

---------------------

## Getting help with R

- `?` and `??`
- Google
- R Stack Exchange

---------------------

## R studio

![Rstudio](images/Rstudio.png)

---------------------

## Basic R Syntax

```
?
#
<-
=
()
{}
[]
:
;
""
```

---------------------

## Basic Commands
###Assigning variables

```
x <- 3
y <- 5.291
z <- 2 * pi

X <- 3.8
Y <- -45
Z <- exp(1)
```

---------------------

## Basic Commands
### Assigning vectors

```
a <- c(11.2, 33.4, 16.7, 13.2, 7.8, -23.5)
b <- c(1:10)
d <- seq(from=0, to=1, by=0.1)
```

---------------------

## Basic Commands
### Assigning variables

```
name <- "Alex"
names <- c("Alex", "Brian", "Conan", "Dave", "Erin", "Franz")
colr <- list("red", "green", "blue")
```

---------------------

## Basic Commands
### Arithmetic
```
+
-
*
/
```

### Powers
```
exp()
^
log()
log10()
```

---------------------

## Basic Commands
### Mathematical functions

```
sum()
abs()
mean()
sd()
sqrt()
```

---------------------


## Data Types

- R treats different data in different ways
- R will automatically select what it thinks is the appropriate data type
- However, you may need/want to specify data types yourself
- R uses numeric and string variables, lists, arrays, matrices, dataframes

---------------------

## Data Types

```
is()

is.na()

as()
```

---------------------

## An example

```
# sample data from the trees dataset
summary(trees)
?trees # tells us about the dataset
### Height is in feet
### Girth (diameter) is in inches measured at 4'6”
### Volume is in cubic feet
radii <- trees$Girth / 2
radii.ft <- radii / 12
volumes <- pi * (radii.ft)^2 * trees$Height
trees$Volume
```

---------------------

# Working with data in R

---------------------

## Importing and viewing data

```
setwd("path/to/data/directory")
data <- read.csv("filename.csv", header=TRUE )
summary(data)
```

```
head(data)
tail(data)
names(data)
```

```
which()
```

---------------------

## Using additional packages

```
install.packages("plyr")
require(plyr)
```

---------------------

## Sample R script

```
# change working directory
setwd("path/to/working/directory")

# install/load additional packages
if (!require(lme4)) {
	install.packages("lme4"); library(lme4)
}

# import data
data <- read.csv("filename.csv, header="TRUE")

# first-look at the data
head(data)
summary(data)

# clean up data
...

# visualize the data
...

# analyse the data
...

```

---------------------

## Control operators

---------------------

### Conditional statements

```
if (condition1) {
	doThisThing
} else {
	doAnotherThing
}
```

### Evaluation of conditions

```
<
>
==
<=
<=
!=
&&
||
```

---------------------

### Loops
- `for` loops are used when the number of iterations in *known*
- `while` loops are used when the number of iterations is *unknown*

```
pies <- numeric(100)
for (i in 1:length(pies)) {
	pies[i] <- pi * i
}
```

```
x <- 0; done=FALSE
while (!done) {
	if (x > 23) {
		done = TRUE
	} else {
		x <- x + pi
	}
	print(x, digits=4)
}
```
