Lining
===========

The underpinning of good design
-------------------------------

### How does it work
Lining uses SCSS to generate the CSS for basic structural layouts. In the `lining.scss` file you'll several lines of code that look this:
<code>
@include layout(12, 960px, fixed);
</code>
Each line generates the CSS for a specific type of layout and is customized. The attributes specified in the "layout" mixin are number of columns, overall width and type of layout (fixed or layout). Liquid layouts look like this:

<code>
@include layout(3, 100%, liquid);
</code>
That's 3 columns, 100% width, liquid layout. To modify the layout simply change these attributes.

### Fixed width
In the HTML, just specify the ammount of columns and type of layout as shown below.
<pre><code>
<div class="lining-fixed">
	<div class="group-fixed-5">
		<div class="unit-fixed pos1"></div>
		<div class="unit-fixed pos2"></div>
		<div class="unit-fixed pos3"></div>
		<div class="unit-fixed pos4"></div>
		<div class="unit-fixed pos5"></div>
	</div>
</div>
</code></pre>

### Liquid
<pre><code>
<div class="lining-liquid">
	<div class="group-liquid-3">
		<div class="unit-liquid pos1"></div>
		<div class="unit-liquid pos2"></div>
		<div class="unit-liquid pos3"></div>
	</div>
</div>
</pre></code>

