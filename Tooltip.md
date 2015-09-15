## Introduction ##

**Tooltip** is a [jQuery](http://www.jquery.com) plugin to add simple tooltip support to your web development.

Its only 6Kb (in its non-packed version with full comments) and, even it's in a development stage, it's full usable.

## How to use ##

  1. Include your jQuery library. You can download it from [here](http://code.google.com/p/jqueryjs/)
  1. Include the Tooltip library. You can download it from [here](http://xphere-jquery-plugins.googlecode.com/files/xph.tooltip.v0.7b.js)
  1. Call this code: `$('#id').tooltip({text: 'This is a tooltip!'});`

Now whenever you point your mouse at the HTML element identified by 'id', the tooltip must show.

## Default options ##

The `tooltip()` function takes one parameter, _options_, which defines how the tooltip behaviour will be.

When an option is not defined, its value is taken from the $.tooltip.defaults variable.

You can change default behaviour with the `$.tooltip.setup({options})` function.

`$.tooltip.setup({text:'Tooltip text by default!'})`

## Option list ##

  * ### class _(default: 'tooltip')_ ###
> This class is applied to the tooltip container when shown.

  * ### css _(default: {})_ ###
> This CSS is applied to the tooltip container when shown.

  * ### dst _(default: null)_ ###
> If set to an HTML object, it is used as the tooltip container.

> If null, a new container is created every time the tooltip must be shown, and destroyed when hide.

  * ### duration _(default: null)_ ###
> If defined, time to wait between showing and hiding the tooltip.

> If not defined, it lasts until mouseout event raises.

  * ### event _(default: 'mouseover')_ ###
> The event that fires the tooltip.

> By default, it's shown on mouse over.

  * ### href _(default: null)_ ###
> Text to be shown as an url.

  * ### in _(default: null)_ ###
> If defined, the waiting time, in miliseconds, between the event raising and the moment the tooltip must show.

> If null, the tooltip shows inmediately.

  * ### offset _(default: {x: 12, y: 18})_ ###
> Offset in pixels from the current mouse position to the top-left corner of the container.

> Only applied when 'track' option is true.

  * ### onhide _(default: null)_ ###
> Callback function to be called whenever the tooltip hides.

  * ### onshow _(default: null)_ ###
> Callback function to be called whenever the tooltip shows.

  * ### out _(default: null)_ ###
> If defined, the waiting time, in miliseconds, between the moment the mouse goes out the element and the moment the tooltip should hide.

> If null, the tooltip hides inmediately.

  * ### smart _(default: false)_ ###
> If true, the plugin will try to fill 'title', 'text' and 'href' options, when undefined.

> Usually taken from the element attributes 'title', 'alt' and 'href' respectively.

  * ### text _(default: null)_ ###
> Text to be shown inside the tooltip.

  * ### title _(default: null)_ ###
> Text to be shown as a title in the first row of the tooltip.

  * ### track _(default: true)_ ###
> If true, the tooltip container will follow the mouse when moving.

## How to CSS ##

By default, the tooltip container is marked with a 'tooltip' class.

The content is added in three different <div>'s, marked as 'title', 'text' and 'url' classes.<br>
<br>
So, a common CSS for tooltip could be:<br>
<br>
<pre><code>.tooltip {<br>
  background-color:#FFF;<br>
  border:1px solid #000;<br>
}<br>
<br>
.tooltip .title {<br>
  background-color:#000;<br>
  border-bottom:1px solid #FFF;<br>
  font-size:x-small;<br>
  font-weight:bold;<br>
  text-align:center;<br>
  padding:.5ex 2ex;<br>
}<br>
<br>
.tooltip .text,<br>
.tooltip .url {<br>
  padding:.4ex .7ex .2ex;<br>
  font-size:xx-small;<br>
}<br>
<br>
.tooltip .url {<br>
  font-weight:bold;<br>
}<br>
<br>
.tooltip .url:before {<br>
  content: 'url: ';<br>
}<br>
</code></pre>

Remember that you can change the tooltip class with the 'class' option.<br>
<br>
<h2>Advanced features</h2>

Tooltip plugin can take advantage if the <a href='http://plugins.jquery.com/project/metadata'>Metadata</a> plugin is loaded.<br>
<br>
HTML markup:<br>
<pre><code>...<br>
&lt;a class="{tooltip: {title: 'This is a LINK'}}" href="link1.html"&gt;link 1&lt;/a&gt;<br>
&lt;a class="{tooltip: {text: 'This is another LINK'}}" href="link2.html"&gt;link 2&lt;/a&gt;<br>
&lt;a class="{tooltip: {smart: true, in:2000}}" href="link3.html"&gt;link 3&lt;/a&gt;<br>
...<br>
</code></pre>

JS code:<br>
<pre><code>...<br>
$('a').tooltip();<br>
...<br>
</code></pre>

As easy as this!