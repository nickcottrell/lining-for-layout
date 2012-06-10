Lining
===========

CSS grid framework
------------------

### How does it work
Lining uses [SCSS](http://sass-lang.com/) to generate CSS that provides basic structure to your web layout. In the `lining.scss` file, you'll see several lines of code that look this:
	
	@include layout(12, 960px, fixed);
	
Each line generates the CSS for a specific type of layout and is customizable. The attributes specified in the "layout" mixin are number of columns, overall width and type of layout (fixed and liquid shown here). In the [demo](http://istitch.net/lining-for-layout
), liquid layouts look like this:

	@include layout(3, 100%, liquid);

That's 3 columns, 100% width, liquid layout. To modify the layout simply change these attributes. The code provided here supports liquid and fixed layouts-- 1 to 12 columns each. Feel free to simply use the `compiled.css` file if you're not in to all this SCSS/SASS stuff Out of the box, you can spec the styles as shown in the markup below.

In the HTML, just specify the amount of columns and type of layout as shown below.

### Fixed*
	<div class="lining-fixed">
		<div class="group-fixed-5">
			<div class="unit-fixed pos1"></div>
			<div class="unit-fixed pos2"></div>
			<div class="unit-fixed pos3"></div>
			<div class="unit-fixed pos4"></div>
			<div class="unit-fixed pos5"></div>
		</div>
	</div>

### Liquid*
	<div class="lining-liquid">
		<div class="group-liquid-3">
			<div class="unit-liquid pos1"></div>
			<div class="unit-liquid pos2"></div>
			<div class="unit-liquid pos3"></div>
		</div>
	</div>
	*feel free to re-name to fulfil your semantic markup purist desires


### Offsetting
In this system, there is no need to add an `offset` attribute as seen in other CSS grid frameworks. Simply omit the `pos` number that you want to skip. The [demo](http://istitch.net/lining-for-layout
) shows this in the blank fourth column of the liquid layout.

	<div class="lining-liquid">
		<div class="group-liquid-5">

			<div class="unit-liquid pos1"><p>...</p></div>
			<div class="unit-liquid pos2"><p>...</p></div>
			<div class="unit-liquid pos3"><p>...</p></div>
			<!--skipped .pos4 on purpose to show how it offsets-->
			<div class="unit-liquid pos5"><p>...</p></div>

		</div><!--end .group-liquid-->
	</div><!--end .lining-liquid -->


### Demo
[http://istitch.net/lining-for-layout] (http://istitch.net/lining-for-layout)

### Semantic Vs. Pragmatic
I believe in semantic markup. However, sometimes when you're making a fully customizable, modular layout system, it isn't possible or practical to completely avoid any reference to the presentational elements. I feel that if you have a well-thought-out, nicely structured system, then it will save you all the time in the world for discussions about semantic markup. 

I've attempted to do start the discussion here, by ditching reference to rows and columns in the compiled CSS layer. A few of the class names were chosen for the [demo](http://istitch.net/lining-for-layout
) because it helps make their function more clear (which ironically seems pretty *semantic* to me, btw). Terms like `group`, `unit` and `pos` (position) are used instead of `row`, `col`, etc. The terms for `liquid` and `fixed` are make more sense for the demo but they can easily be changed to something that suits your semantic needs. Unfortunately, the number of columns in the layout is required for now because it's integral to the way the base column widths are calculated. Maybe that'll change someday but maybe not.
   
### Futurelog
I'll be working on adding a layer to make this responsive. Whatever it is will be something very simple that can provide a base level that will be expandable.

