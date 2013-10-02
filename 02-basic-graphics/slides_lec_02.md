% Data Wrangling & Presentation in R
% Lecture 2: Introduction to Base Graphics
% Franz Simon, Alex Chubaty, Sean Anderson, Corey Phillis

---------------------

## Today's Lecture

- Introduction to Base Plot
- Advanced objects using the "structure" command
- Introduction to graphics customization

---------------------

## Plotting in R

- Base Plot
- Grid Graphics
- Lattice Graphics
- `ggplot2` (Lecture topic in two classes)



---------------------

## Structure of Arbitrary Objects

- Functions in R require specific objects are arguments
- Being able to access specific elements of custom objects in R
- `str()`

---------------------

## Base Plotting

- Plot your data with `plot()`

---------------------

## Scatter Plots

```
plot(x, y)
points(x,y)	### adds x vs y points to existing plot
curve(x)	### plots continuous data / functions

### create a sequential palette for usage and show colors
abline(v=seq(1, 10, 2), lty=2, col="blue")
```

---------------------

## Saving your Graphs

```
pdf("charmander.pdf", width=5, height=5) ### Dimensions in inches
jpeg("charmander.jpg", width=500, height=500) ### Size in pixels
jpeg("charmander.jpg", width=500, height=500, units="in") ### Or px, cm, or mm 
dev.off() ### turns off the plotting device
```


---------------------

## Bar Graphs

- Discrete independent variable
- Continuous response variable

```
barplot(x, y)
as.factor(x)
```

---------------------

## Histograms

- Approximation of a probability density function.

```
hist(x, y, breaks=10)
hist(x, y, breaks=10, freq=FALSE)
curve(dnorm(x, mean=mean(y), sd=sd(y)), add=TRUE)
```

---------------------

## Box & Whisker Plots

- Graph factors based on their quartiles

```
boxplot(mpg ~ cyl, data=mtcars, main="Car Milage Data",
	xlab="Number of Cylinders", ylab="Miles Per Gallon")
```

- Another solution are violin plots (`vioplot`)

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
 
```
display.brewer.all() ###

install.packages("RColorBrewer") ###
require(RColorBrewer) ###
my.palette <- brewer.pal(7, "Greens") ### create a sequential palette for usage and show colours
image(1:7, 1, as.matrix(1:7), col=my.palette )
```

---------------------

## Customizing the axis

- Two ways of dealing with axes
    - Inside the plot command
    - Using the function `axis()`
    - `axis(side, at = NULL, labels = TRUE, tick = TRUE, ...)`

---------------------

## Points

```
plot(x , y1, pch 2, cex = 3, ity= 5)
points(x, y2, pch=3, type="p") ### Adds points to a graph
points(x, y2, pch=3, type="l") ### Adds lines a graph
points(x, y2, pch=3, type="b") ### Adds points and lines a graph
```

---------------------

## Specifying additional plot parameters

```
curve(x^2,xlim=c(-10,10),col=”blue”,lwd=2)
curve(0.5*x^2,xlim=c(-10,10),col=”red”,add=TRUE)
abline(v=0)

pch ### (point character)
lty ### (line type)
lwd ### (line width)
cex ### (character expansion)
```

`xlab, ylab, main ### (axis/main labels)`

---------------------

## Legends

```
legend("top", legend=LETTERS[1:6])
```

---------------------

## Adding Text

```
text(location, "text to place", pos, ...)

mtext("text to place", side, line=n, ...) ### Write in the margins
```


---------------------

## Whole new world (Polygons)

```
polygon(x, y = NULL, density = NULL, angle = 45,
        border = NULL, col = NA, lty = par("lty"),
        ..., fillOddEven = FALSE)
```

---------------------

