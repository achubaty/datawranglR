% Data Wrangling & Presentation in R
% Lecture 2: Introduction to Base Graphics
% Alex Chubaty, Franz Simon, Sean Anderson, Corey Phillis
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

- str()

---------------------

## Base Plotting

- Base plot is done mostly with `plot()`

---------------------

## Scatter Plots

- `plot(x, y)`
- # add solid horizontal lines at y=1,5,7 
- abline(h=c(1,5,7))
- # add dashed blue verical lines at x = 1,3,5,7,9
- abline(v=seq(1,10,2),lty=2,col="blue")

---------------------

## Saving your Graphs


`pdf(save = "charmander.pdf")`
`jpeg(save = "charmander.pdf")`
`dev.off()`


---------------------

## Bar Graphs

- Discrete independent 
- continous reponse variable
- `barplot(x , y)`
- `as.factor(x)`

---------------------

## Histograms

- Approximation of a probablility density funciton.
- `hist(x , y)`

---------------------

## Box Plots

- Graph factors based on their quartiles
- `boxplot()`
- Another solution are violon plots

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

---------------------

## Points

 - `plot(x , y, pch = 2, cex = 3, ity= 5)`

---------------------

## Legends

- `legend("top", legend = LETTERS[1:6])`

---------------------

## Adding Text

- `text(location, "text to place", pos, ...)`
- `mtext("text to place", side, line=n, ...)`


---------------------

## Whole new world 
- Polygons

---------------------

