Lining
===========

The underpinning of good design
-------------------------------

### How does it work
Lining uses [SCSS](http://sass-lang.com/) to generate CSS that provides basic structure to your web layouts. In the `lining.scss` file, you'll see several lines of code that look this:
	
	@include layout(12, 960px, fixed);
	
Each line generates the CSS for a specific type of layout and is customizable. The attributes specified in the "layout" mixin are number of columns, overall width and type of layout (fixed or liquid). Liquid layouts look like this:

	@include layout(3, 100%, liquid);

That's 3 columns, 100% width, liquid layout. To modify the layout simply change these attributes. In the HTML, just specify the amount of columns and type of layout as shown below.

### Fixed width
	<div class="lining-fixed">
		<div class="group-fixed-5">
			<div class="unit-fixed pos1"></div>
			<div class="unit-fixed pos2"></div>
			<div class="unit-fixed pos3"></div>
			<div class="unit-fixed pos4"></div>
			<div class="unit-fixed pos5"></div>
		</div>
	</div>

### Liquid
	<div class="lining-liquid">
		<div class="group-liquid-3">
			<div class="unit-liquid pos1"></div>
			<div class="unit-liquid pos2"></div>
			<div class="unit-liquid pos3"></div>
		</div>
	</div>

### Semantic Vs. Pragmatic
I believe in semantic markup. However, sometimes when you're making a fully customizable, modular layout system, it isn't possible or practical to completely avoid any reference to the presentational elements. I feel that if you have a well-thought-out, nicely structured system, then it will save you all the time in the world for discussions about semantic markup. 

I've attempted to do start the discussion here, by ditching reference to rows and columns in the compiled CSS layer. A few of the class names were chosen for the demo because it helps make their function more clear (which ironically seems pretty semantic to me, btw). Terms like `group`, `unit` and `pos` (position) are used instead of `row`, `col`, etc. The terms for `liquid` and `fixed` are required if you want to featured both in your layout, but can easily be changed to something that suits your semantic needs. Unfortunately, the number of columns in the layout is required. My next step will be to make that a configurable thing so that you can name the 'liquid' layout whatever you want and have multiple layout types and layout names. It's all possible now, though so go ahead and re-name everything to meet your semantically pure needs!
   
