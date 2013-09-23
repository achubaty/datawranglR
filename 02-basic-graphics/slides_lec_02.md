% Data Wrangling & Presentation in R
% Lecture 2: Introduction to Base Graphics
% Franz Simon, Alex Chubaty, Sean Anderson, Corey Phillis
% Fall 2013

---------------------

## Today's Lecture

- Introduction to Base Plot
- Advaneced objects using Structure()
- Introduction to graphics customization

---------------------

## Plotting in R

- Base Plot
- Grid Graphics
- Lattice Graphics
- ggplot2 (Next lecture's topic)



---------------------

## Structure of Arbitrary Objects

- Functions in R require specific objects are arguments
- Being able to access specific elements of custum objects in R
- `str()`

---------------------

## Base Plotting

- Plot your data with `plot()`

---------------------

## Scatter Plots

- `plot(x, y)`
- `points(x,y)`	### adds x vs y points to existing plot
- `curve(x)`		### plots continuous data / functions
- # add dashed blue verical lines at x = 1,3,5,7,9
- `abline(v=seq(1,10,2),lty=2,col="blue")`

---------------------

## Saving your Graphs


- `pdf(save = "charmander.pdf", width = 5, height = 5 )` ### Dimensions in inches
- `jpeg(save = "charmander.pdf", width = 500, height = 500)` ### Size in pixels
- `jpeg(save = "charmander.pdf", width = 500, height = 500, units= "in")` ### Or px, cm, or mm 
- `dev.off()` ### turns off the plotting device


---------------------

## Bar Graphs

- Discrete independent 
- continous reponse variable
- `barplot(x , y)`
- `as.factor(x)`

---------------------

## Histograms

- Approximation of a probablility density funciton.
- `hist(x , y, breaks = 10)`
- curve(dnorm(x, mean=mean(y), sd=sd(y)), add=TRUE)


---------------------

## Box Plots

- Graph factors based on their quartiles
- `boxplot(mpg ~ cyl, data = mtcars, main="Car Milage Data", xlab = "Number of Cylinders", ylab="Miles Per Gallon")`
- Another solution are violin plots

---------------------

## Customization
- Colour
- Legends
- Axes and Text
- Points

---------------------

## Colour

- Text
- RGB
- CMYK
- HEX

---------------------

## Colour Brewer

- [Colour Brewer](http://colorbrewer2.org/)

---------------------

## Customizing the axis

- Two ways of dealing with axes
    - Inside the plot command
    - Using the function `axis()`
    - `axis(side, at = NULL, labels = TRUE, tick = TRUE, ...)`

---------------------

## Points

 - `plot(x , y, pch = 2, cex = 3, ity= 5)`
 - 

---------------------

## Specifying additional plot parameters
- `curve(x^2,xlim=c(-10,10),col=”blue”,lwd=2)`
- `curve(0.5*x^2,xlim=c(-10,10),col=”red”,add=TRUE)`
- `abline(v=0)`

- `pch` ### (point character)
- `lty` ### (line type)
- `lwd` ### (line width)
- `cex` ### (character expansion)
- `xlab, ylab, main` ### (axis/main labels)

---------------------

## Legends

- `legend("top", legend = LETTERS[1:6])`

---------------------

## Adding Text

- `text(location, "text to place", pos, ...)`
- `mtext("text to place", side, line=n, ...)` ### Write in the margins


---------------------

## Whole new world 
- Polygons

---------------------

