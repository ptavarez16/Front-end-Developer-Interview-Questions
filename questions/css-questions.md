# CSS Questions:

### What is CSS selector specificity and how does it work?
Specificity is a weight that is applied to a given CSS declaration, determined by the number of each selector type in the matching selector. When multiple declarations have equal specificity, the last declaration found in the CSS is applied to the element. Specificity only applies when the same element is targeted by multiple declarations. As per CSS rules, directly targeted elements will always take precedence over rules which an element inherits from its ancestor.
  
### What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
CSS resets aim to remove all built-in browser styling. Standard elements like h1 - h6, p, strong, em end up looking exactly alike, having no decoration at all. You're then supposed to add all decoration yourself.

Normalize.css aims to make built-in browser styling consistent across browsers. Elements like h1 - h6 will appear bold and larger in a consistent way across browsers. You're then supposed to add only the difference in decoration your design needs.

If I had to choose, I will chose Normalize.css. I feel like having elements render the same consistently across all browsers is important. Also, resetting everything just to restyle again seems counter productive to me.
  
### Describe Floats and how they work.
Float is a CSS positioning property. Floated elements remain part of the flow of the web page. There are four valid values for the float property: left, right, none, inherit.

A floated element will move as far to the left or right as it can. Usually this means all the way to the left or right of the containing element. The elements after the floating element will flow around it. The elements before the floating element will not be affected.

### Describe z-index and how stacking context is formed.
The z-index property can be specified with an integer value (positive, zero, or negative), which represents the position of the element along the z-axis. If you are not familiar with the z-axis, imagine the page as a stack of layers, each one having a number. Layers are rendered in numerical order, with larger numbers above smaller numbers.
  
### Describe BFC(Block Formatting Context) and how it works.
A block formatting context is a part of a visual CSS rendering of a Web page. It is the region in which the layout of block boxes occurs and in which floats interact with other elements.
  
### What are the various clearing techniques and which is appropriate for what context?
.clearfix method:
- The .clearfix hack uses a clever CSS pseudo selector (:after) to clear floats. Rather than setting the overflow on the parent, you apply an additional class like clearfix to it.

```css
.group:after {
  content: "";
  display: table;
  clear: both;
}
```

Empty div method:
- `<div style="clear:both;"></div>`

`overflow: auto` or `overflow: hidden` method:
- Parent will establish a new block formatting context and expand to contains its floated children.

### How would you approach fixing browser-specific styling issues?
- When the issue and offending browser is identified, I would look into how to create a seperate styling sheet that would only load when that specific browser is being used.
- Use a library like Bootstrap that handles this for me

### How do you serve your pages for feature-constrained browsers?
  #### What techniques/processes do you use?
- Graceful degradation
  - The practice of building an application for modern web browsers while ensuring it remains functional in older browsers.
- Progressive enhancement
  - The practice of building an application for a base level of user experience, but adding functional enhancements when a browser supports it.
- Use sites like caniuse.com to check for feature support
  
### What are the different ways to visually hide content (and make it available only for screen readers)?
- `visibility: hidden`
  - However, the element is still in the flow of the page so it will take up space.
- `width: 0; height: 0`
  - If the element does not take up any space, then it will not show up!
- `postion; absolute; left: -99999px`
  - Postion the content outside of the screen

### Have you ever used a grid system, and if so, what do you prefer?
I've used a grid system with Bootstrap. The system is already built in so you could start using grids right from the moment you download the library!

### Have you used or implemented media queries or mobile specific layouts/CSS?
Yes! All of my apps are responsive. I wanted to make them this way because my friends usually browse my sites on their phone!

### Are you familiar with styling SVG?
Sadly I am not >.<

### Can you give an example of an `@media` property other than `screen`?
`@media print` is used for printers!

### What are some of the "gotchas" for writing efficient CSS?
- Avoid key selectors that match large numbers of elements (tag and universal selectors)
- Prefer class and ID selectors over tag selectors
- Avoid redundant selectors
- Preferably don't use * (universal selector)
- Try to group and reuse common properties.

### What are the advantages/disadvantages of using CSS preprocessors?
- Advantages:
  - CSS is more maintainable
  - Easy to write nested selectors
  - Variables for consistent theming
  - Mixins to generate repeated CSS
  - Splitting code into multiple files in a more efficient way
- Disadvantages:
  - Tools required for preprocessing
  - Re-compilation time can be slow

#### Describe what you like and dislike about the CSS preprocessors you have used.
- Likes:
  - Mostly the advantages listed above
  - Less is written in JavaScript
  - Looks cleaner and more legible
- Dislikes
  - Don't really have anything to dislike. I use Sass which is a great preprocessor in my opinion
  
### How would you implement a web design comp that uses non-standard fonts?
- Use `@font-face` and define `font-family` for different `font-weight`s
- Link to webfont as a stylesheet, use `@import`, or JS

### Explain how a browser determines what elements match a CSS selector.
This part is related to the above about writing efficient CSS. Browsers match selectors from rightmost (key selector) to left. Browsers filter out elements in the DOM according to the key selector, and traverse up its parent elements to determine matches. The shorter the length of the selector chain, the faster the browser can determine if that element matches the selector.

### Describe pseudo-elements and discuss what they are used for.
A CSS pseudo-element is a keyword added to a selector that lets you style a specific part of the selected element(s). They can be used for decoration (`:first-line`, `:first-letter`) or adding elements to the markup (combined with `content: ...`) without having to modify the markup (`:before`, `:after`).

### Explain your understanding of the box model...
- The CSS box model is responsible for calculating:
  - How much space a block-level element takes up.
  - Whether or not borders and/or margins overlap, or collapse.
  - A box's dimensions.
- The box model has the following rules:
  - The dimensions of a block element are calculated by width, height, padding, borders, and margins.
  - If no height is specified, a block element will be as high as the content it contains, plus padding (unless there are floats).
  - If no width is specified, a non-floated block element will expand to fit the width of its parent minus padding.
  - The height of an element is calculated by the content's height.
  - The width of an element is calculated by the content's width.
  - By default, paddings and borders are not part of the width and height of an element.

#### How you would tell the browser in CSS to render your layout in different box models?
```box-sizing: border-box``` or ```box-sizing: content-box```

### What does ```* { box-sizing: border-box; }``` do? What are its advantages?
`box-sizing: border-box` changes how the width and height of elements are being calculated, border and padding are also being included in the calculation.

### What is the CSS `display` property and can you give a few examples of its use?
The display CSS property specifies the type of rendering box used for an element. In HTML, default display property values are taken from behaviors described in the HTML specifications or from the browser/user default stylesheet.

- Display types:
  - none
  - block
  - inline
  - inline-block
  - table
  - table-row
  - table-cell
  - list-item

### What's the difference between inline and inline-block?
Elements with `display:inline-block` are like `display:inline` elements, but they can have a width and a height. That means that you can use an inline-block element as a block while flowing it within text or other elements.

- Difference of supported styles as summary:
  - inline: only margin-left, margin-right, padding-left, padding-right
  - inline-block: margin, padding, height, width

### What's the difference between a relative, fixed, absolute and statically positioned element?
A positioned element is an element whose computed position property is either relative, absolute, fixed or sticky.
- static: The default position; the element will flow into the page as it normally would. The top, right, bottom, left and z-index properties do not apply.
- relative: The element's position is adjusted relative to itself, without changing layout (and thus leaving a gap for the element where it would have been had it not been positioned).
- absolute: The element is removed from the flow of the page and positioned at a specified position relative to its closest positioned ancestor if any, or otherwise relative to the initial containing block. Absolutely positioned boxes can have margins, and they do not collapse with any other margins. These elements do not affect the position of other elements.
- fixed: The element is removed from the flow of the page and positioned at a specified position relative to the viewport and doesn't move when scrolled.
- sticky: Sticky positioning is a hybrid of relative and fixed positioning. The element is treated as relative positioned until it crosses a specified threshold, at which point it is treated as fixed positioned.

### What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
I have only used Bootstrap. Something I would change is the dropdown component for mobile view. When a selection is made, the dropdown should slide back up but that is not the case.

### Have you played around with the new CSS Flexbox or Grid specs?
I have not, but it's something I've been wanting to get into!

### Can you explain the difference between coding a web site to be responsive versus using a mobile-first strategy?
Both responsive and mobile-first strategy attempt to optimize the user experience across different devices, adjusting for different viewport sizes, resolutions, usage contexts, control mechanisms, and so on.

Responsive design works on the principle of flexibility — a single fluid website that can look good on any device. Responsive websites use media queries, flexible grids, and responsive images to create a user experience that flexes and changes based on a multitude of factors. Like a single ball growing or shrinking to fit through several different hoops.

Adaptive design is more like the modern definition of progressive enhancement. Instead of one flexible design, mobile-first strategy detects the device and other features, and then provides the appropriate feature and layout based on a predefined set of viewport sizes and other characteristics. The site detects the type of device used, and delivers the pre-set layout for that device. Instead of a single ball going through several different-sized hoops, you’d have several different balls to use depending on the hoop size.

### Have you ever worked with retina graphics? If so, when and what techniques did you use?
I have not, but would love to learn how!

### Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?
`translate()` is a value of CSS transform. Changing transform or opacity does not trigger browser reflow or repaint, only compositions, whereas changing the *absolute positioning* triggers reflow. transform causes the browser to create a GPU layer for the element but changing *absolute positioning* properties uses the CPU. Hence `translate()` is more efficient and will result in shorter paint times for smoother animations.

When using `translate()`, the element still takes up its original space (sort of like position: relative), unlike in changing the *absolute positioning*.
