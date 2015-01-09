Lining
===========

Super simple, slightly semantic grid system
-------------------------------------------

### How does it work
Lining uses [SCSS](http://sass-lang.com/) to generate CSS that provides basic structure to your web layout. In the `lining.scss` file, you'll see mixins that look this:
	
	@include lining-fixed(12, 960px, fixed);

Each line generates the CSS for a specific type of layout and is customizable. The attributes specified in the "layout" mixin are number of columns, overall width and type of layout (fixed and liquid shown here). In the [demo](http://istitch.net/lining-for-layout
), liquid layouts look like this:

	@include lining-liquid(3, 100%, liquid);

That's 3 columns, 100% width, liquid layout. To modify the layout simply change these attributes. The code provided here supports liquid and fixed layouts, 12 columns each. Feel free to simply use the `lining-compiled.css` file if you're not in to all this SCSS/SASS stuff. Out of the box, you can spec the styles as shown in the markup samples.

In the HTML, just specify the amount of columns and type of layout as shown below.

### Fixed*
	<div class="fixed">
		<div class="group">
			<div class="item"></div>
			<div class="item"></div>
			<div class="item"></div>
			<div class="item"></div>
			<div class="item"></div>
		</div>
	</div>

### Liquid*
	<div class="lining">
		<div class="group">
			<div class="item"></div>
			<div class="item"></div>
			<div class="item"></div>
		</div>
	</div>
	*feel free to re-name the mixin and fulfil your semantic markup purist desires

### Spanning
An important layout feature is to be able to span 2 or more columns in a layout. This is because most of the time, you'll want to set up a grid that contains the max number of columns, and then span across multiple columns, which allows you to vary the width of your columns in a layout. This supports grid structures such as a two-thirds one-third layout.

	<div class="liquid">
		<div class="group">

			<div class="item span-2">...</div>
			<!--no unit #2 here-->
			<div class="item">...</div>
			<div class="item">...</div>
			<div class="item">...</div>

		</div>
	</div>


### Offsetting
To skip over a section of the grid, add the "skip-#" class and specify how many units you want to skip.

	<div class="liquid">
		<div class="group">

			<div class="item">...</div>
			<div class="item">...</div>
			<div class="item">...</div>
			<!--no item #4 here-->
			<div class="item skip-1">...</div>

		</div>
	</div>


### Responsive
The layout shown here is responsive, meaning that its attributes change depending on the screen size of the device in which it's viewed. To see how a mobile device might look, simply re-size the screen.

	@media screen and (min-width: 770px) {
		@include lining-fixed(3, 960px, fixed);
		@include lining-liquid(5, 80%, liquid);
	}
		
	
This works by wrapping the "lining" styles in a "@media" query which has a set screen size. The demo is set at 770px so the "lining" styles kick in at 770px. That means the layout defined by the sass includes will display on screens 770px and beyond. Below 770px will show up as the default. This supports the [*mobile first*](http://www.abookapart.com/products/mobile-first) approach and can be adjusted for any screen size. 


#### What about IE 6-8???
Lining for layout uses *@media* queries for its responsive layer. Unfortunately this is only supported in IE9 and above. However, there is an awesome bit of JavaScript that you can use to make it work in older versions of IE (6-8). Simply add the [Respond.js](https://github.com/scottjehl/Respond) script. 

Note: The Demo contains the [Respond.js](https://github.com/scottjehl/Respond) JavaScript.



### Not into SASS?
You can just use the compiled version: `lining-compiled.css`. It supports a 12 column, 960px, fixed layout and a 12 column, 100% width, liquid layout. No need for SASS because we already compiled the following for you.

	@include lining-fixed(12, 960px, fixed);
	@include lining-liquid(12, 100%, liquid);
	
Note: if you don't want responsive, simply remove the media query.


### Demos
[http://istitch.net/lining-for-layout] (http://istitch.net/lining-for-layout)

### Semantic Vs. Pragmatic
I believe in semantic markup. However, sometimes when you're making a fully customizable, modular layout system, it isn't possible or practical to completely avoid any reference to the presentational elements. I feel that if you have a well-thought-out, nicely structured system, then it will save you all the time in the world for discussions about semantic markup. 

I've attempted to do start the discussion here, by ditching reference to rows and columns in the compiled CSS layer. A few of the class names were chosen for the [demo](http://istitch.net/lining-for-layout
) because it helps make their function more clear (which ironically seems pretty *semantic* to me, btw). Terms like `group`, `item` and `pos` (position) are used instead of `row`, `col`, etc. The terms for `liquid` and `fixed` are make more sense for the demo but they can easily be changed to something that suits your semantic needs. Unfortunately, the number of columns in the layout is required for now because it's integral to the way the base column widths are calculated. Maybe that'll change someday but maybe not.
   


