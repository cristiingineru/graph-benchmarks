## ni-chart

> A custom element that allows to chart one or multiple data sets.

The difference between a graph and a chart is that a graph plots directly the data
sets provided but the chart uses a buffer of historical values, called a
HistoryBuffer for data handling.

As you append new values to the charts' History buffer the chart is updated as
needed, on the next browser animation frame.

Example:

```html
<ni-chart id="chart1" bufferSize="1024">
    <ni-cartesian-axis show label="Time" axis-position="bottom"></ni-cartesian-axis>
    <ni-cartesian-axis show label="Amplitude" axis-position="left"></ni-cartesian-axis>
    <ni-cartesian-plot show label="Plot 1">
      <ni-cartesian-plot-renderer line-width="2" line-stroke="#a84716"></ni-cartesian-plot-renderer>
    </ni-cartesian-plot>
</ni-chart>

<script>
  var historyBuffer = $('#chart1').getHistoryBuffer();

  // write 1000 values into the chart's history buffer
  for (var i = 0; i < 10; i++) {
    historyBuffer.push(Math.sin(i));
    i += 0.01;
  }
</script>
```

The HistoryBuffer API is described [here](historyBuffer.md).

## Data types supported by ni-chart

To add data to the chart you need to write it into the history buffer. Here are
examples for adding numbers and arrays of numbers to the history buffer.

* **Numbers**
```js
    var chart = document.querySelector('#myChart');
    var hb = chart.getHistoryBuffer();

    hb.push(5); // add 5 to the history buffer
```
This will render a single plot

* **multiple Numbers**
```js
    var chart = document.querySelector('#myChart');
    var hb = chart.getHistoryBuffer();

    hb.push([5, 7, 8]); // adds 5 to first data series,
                        // 7 to the second one and 8 to the third one
```
This will render 3 plots

* **array of Numbers**
```js
    var chart = document.querySelector('#myChart');
    var hb = chart.getHistoryBuffer();

    hb.appendArray([5, 7, 8]); // add 5, 7 and 8 to first data series
```
This will render a single plot.

* **arrays of arrays of Numbers**
```js
    var chart = document.querySelector('#myChart');
    var hb = chart.getHistoryBuffer();

    hb.appendArray([[5, 7], [8, 9]]); // add 5 and 7 to first data series
                                     // and 8 and 9 to the second one
```
This will render two plots.


When writing values to multiple plots make sure the history buffer is the same
size as the number of data series you write to. Use [history buffer's](historyBuffer.md) *setWidth*
method to change the number of data series in the chart.


### ni-chart properties

**buffer-size** (number) - the size of the chart history buffer 

### ni-chart methods

**setHistoryBuffer(historyBuffer)** - changes the internal history buffer
   of the chart to the provided one

**getHistoryBuffer()** - returns a reference to the internal history
   buffer of the chart
