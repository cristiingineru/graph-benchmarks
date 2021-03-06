## ni-intensity-graph

> A custom element that allows to plot a 2D data set as a gradient map.

An ni-intensity-graph is a declarative way, that uses custom elements, to add an
intensity graph to a web page. Specify your data sets using the value attribute
and customize how the data is renderended using nested custom elements such as
*ni-cartesian-axis*, *ni-color-scale*.

Example:
```html
<ni-intensity-graph id="graph1" value="[[0.1, 0.2], [0.3, 0.4], [0.5, 0.6]]">
    <ni-cartesian-axis label="X" show show-label axis-position="bottom" grid-lines></ni-cartesian-axis>
    <ni-cartesian-axis label="Y" show show-label axis-position="left" grid-lines></ni-cartesian-axis>
    <ni-color-scale label="Color Scale" show show-label
        markers='[{"value":0,"color":"rgba(0,0,0,1)"},{"value":50,"color":"rgba(0,0,255,1)"},{"value":100,"color":"rgba(255,255,255,1)"}]'
        high-color="rgba(255,255,255,1)" low-color="rgba(0,0,0,1)">
    </ni-color-scale>
</ni-intensity-graph>
```
