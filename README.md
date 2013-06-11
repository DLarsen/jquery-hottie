JQuery Hottie Plugin
====================

    "Awesome! You just saved my life."  - JQuery Hottie User.

Easy heatmap-style background-coloring for HTML elements.

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

    <table id="myTable">
        <tr><td>2.59</td><td>0.68</td><td>1.35</td><td>1.35</td><td>2.03</td><td>1.60</td></tr>
        <tr><td>1.39</td><td>0.70</td><td>1.22</td><td>1.08</td><td>1.00</td><td>2.12</td></tr>
        <tr><td>2.87</td><td>0.59</td><td>1.22</td><td>0.57</td><td>1.08</td><td>3.00</td></tr>
        <tr><td>0.99</td><td>0.25</td><td>0.48</td><td>0.50</td><td>0.99</td><td>1.77</td></tr>
    </table>

    $("#myTable td").hottie({
        colorArray : [ 
            "#63BE7B",
            "#FBE983",
            "#F8696B"
        ]
    });

See this all in an <a href="http://jsfiddle.net/larsenal/zVPka/">example on JSFiddle</a>.
