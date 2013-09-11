% Data Wrangling & Presentation in R
% Alex Chubaty, Franz Simon, Sean Anderson, Corey Phillis
% Fall 2013

---------------------

## ![Rlogo](images/Rlogo.png) + ![mdlogo](images/mdlogo.png)

### Course Instructors

- Alex Chubaty **B7250** [achubaty@sfu.ca](mailto:achubaty@sfu.ca)
- Corey Phillis **B6226** [cphillis@sfu.ca](mailto:cphillis@sfu.ca)
- Franz Simon **B7250** [fsimon@sfu.ca](mailto:fsimon@sfu.ca)
- Sean Anderson **B6226** [scanders@sfu.ca](mailto:scanders@sfu.ca)

---------------------

## Course Highlights

- Meet for 2 hours bi-weekly (6 classes)
- New and experienced R users welcome
- We'll cover:
    - Basic R commands and usage
    - Producing high-quality graphics using R
    - Constructing custom figures
    - Manipulating data quickly
    - Using Markdown + R to generate reproducible reports

---------------------

## Lecture Schedule

- Introduction to Markdown & R
- R base graphics
- Data manipulation in R
- R grid graphics
- Custom and advanced plotting
- Extras and additions

---------------------

## Assignments

- Apply the skills learned and practice using R
- Assignments are due at the start of class
- All assignments will be written in Markdown format

---------------------

# Before we start

- Install R version 3.0.0 or higher from [CRAN](http://cran.stat.sfu.ca)
- Install R Studio from [rstudio.org](http://www.rstudio.com/ide/download/desktop)

---------------------

# Introduction to Markdown

- why use Markdown?
    - philosophy:
        > easy to read; easy to write
    - easily converted to other file types (`.doc`, `.html`, `.pdf`, etc.) using [Pandoc](http://johnmacfarlane.net/pandoc/)
    - text files will always be supported/accessible (non-proprietary file format)
    - text files are happy with Git version control; binary files (e.g., `.doc`, `.docx`) aren't
    - we can easily embed code in our documents
        - advanced annotation of R code

---------------------

## Basic Syntax:

- paragraphs seperated by new line
- emphasis using `**bold**` and `*italics*`
- headers using `#`, `##`, `###`, etc.
- ordered lists using `1.`
- unordered lists using `-`
- blockquotes using `>`
- code using backticks
- links using `[link text](http://link_target)`
- images using `![picture caption](image.jpg)`

---------------------

## Advanced Syntax
- citations (not covered)

---------------------

# Intro to R

---------------------

## What is R?
[www.r-project.org](http://www.r-project.org)
> free software environment for statistical computing and graphics

Cross-platform (Windows, OSX, Linux)

---------------------

## Why use R?

- customization
- complexity
- control
- it's *free*

---------------------

## Using R

- R is a command line tool
    - commands can be entered one line at a time
    - or by executing the contents of a script file
- we will use rstudio IDE
- pressing `⇧` in the R terminal will recall the previous command

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

## R Markdown

- Use R Studio to produce `.Rmd` files
- Embed R code, with solutions and figures

```{r}
summary(cars, eval=TRUE)
```

```{r fig.width=7, fig.height=6}
plot(cars)
```

```
2 + 2 = \`r 2+2\`
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
