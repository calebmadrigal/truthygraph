# truthy-graphy

Usually, when equations are graphed, it's black and white, where black means the sides of the equation are equal, and white means the sides of the equations are not equal. *The idea behind [TruthyGraph](https://truthygraph.github.io/) is to graph equations and see not only where they are equal, but where they are close to equal.* In other words, TruthyGraph graphs the truthiness of an equation at various points in the Cartesian plane.

View live webapp here: <https://truthygraph.github.io/>

# How it works

Say the equation is: *y = x^3*

TruthyGraph parses the equation using [math.js](https://github.com/josdejong/mathjs) to get functions to represent the left and right side of the equation:

* `left(x, y) = y`
* `right(x, y) = x^3`

TruthyGraph then takes each of the `(x, y)` pairs for the windows in view, and plugs them into left and right functions, chooses the color to plot on the graph by doing `abs(left(x, y) - right(x, y))**fuzzy_value`. The point of the fuzzy_value is to allow the user to choose how much error shows up on the graph.

Another way to think of what TruthyGraph is doing, is that it is plotting the error in the 2 sides of the equation at various points in the plane. Of course, where the 2 sides are equal (what other graphing program would show as black), the error is 0 (and TruthyGraph shows most strongly).

