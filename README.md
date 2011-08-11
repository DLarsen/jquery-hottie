JQuery Hottie Plugin
====================

Use this library to get heatmap background-coloring for elements.

In its most simple form, it parses the html contents of the selected elements and parses them as floats.

Given the following markup:

    <ul id="example1">
      <li>1<li>
      <li>2<li>
      <li>3<li>
      <li>4<li>
      <li>5<li>
    </ul>

    $('ul#example1 li').hottie();

Frequently, the numeric values used for coloring will not be found in the contents of the selected elements.  You can pass a function as an option which tells the plug-in how to retrieve the numeric value.


    <ul id="example2">
      <li data-hist="4">Alabama</li>
      <li data-hist="3">Alaska</li>
      <li data-hist="7">Arizona</li>
      <li data-hist="1">Arkansas</li>
      <li data-hist="9">California</li>
      <li data-hist="5">Colorado</li>
    </ul>

    $('ul#example2 li').hottie(
    {
    readValue : function(e) {
      return $(e).attr("data-hist");
    }
    });

You can also pass in a color scheme as an array.  Low order colors correspond to low values.  High order values correspond to high values.

    <ul id="example3">
      <li>1</li>
      <li>2</li>
      <li>3</li>
      <li>4</li>
      <li>5</li>
      <li>6</li>
      <li>7</li>
    </ul>

    $("#example3 li").hottie({
      colorArray : [ 
        "#0000ff",
        "#999999"
      ]
    });
