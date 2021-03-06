## ni-cartesian-plot-renderer

> Describes the way a plot is rendered

The four ways to render a plot are the line renderer, the area fill renderer,
the points renderer and the bar renderer. You can combine these in any way you
like for a single plot and different plots can have different renderers.

The fastest one is the line renderer and this is the recomended one for large
data sets and if you care about performance.

The render can be further customized by using the renderer properties.


### ni-cartesian-plot-renderer properties 

**line-stroke** (string) - the color of the line drawn. Default: 'auto'.
       Accepted values: a CSS color string, an empty string or 'auto'. If an empty string
       is passed the line rendering for the plot is disabled. If 'auto' is passed a color
       will be automatically assigned to the plot.
       

**line-width** (number) - the width of the line. Use 1 for maximum
       performance as thicker lines can be slower, depending on the browser and
       the graphic card used. Default: 1

**line-style** (string) - the style of the line drawn. Default: 'solid'.
       Accepted values: *'solid'*, *'dot'*, *'mediumdash'*, *'dashdot'* and *'largedash'*
       

**area-fill** (string) - the color of the area fill drawn under/over
       the line. Default: ''.
       Accepted values: a CSS color string, an empty string or auto. If an empty string
       is passed the area fill for the plot is disabled. If 'auto' is passed a color
       will be automatically assigned to the fill.
       

**area-base-line** (string) - determines the direction the area fill.
Default: 'zero'. Accepted values:

* 'zero': fill the line towards 0
* '-infinity': fill the line towards -Infinity.
* 'infinity': fill the line towards Infinity.


**bar-fill** (string) - the color of the bars drawn. Default: ''.
       Accepted values: a CSS color string, an empty string or auto. If an empty
       string is passed the bars rendering for the plot is disabled. If 'auto'
       is passed a color will be automatically assigned to the bars.
       

**point-color** (string) - the color of the points drawn. Default: ''.
       Accepted values: a CSS color string, an empty string or auto. If an empty
       string is passed the points rendering for the plot is disabled. If 'auto'
       is passed a color will be automatically assigned to the points.
       

**point-size** (number) - the size of the points drawn. Default: 5.

**point-shape** (string) - determines the shape of the points.
       Default: 'ellipse'. Accepted values: 'ellipse', 'square', 'diamond',
       'triangle', 'cross'
       
