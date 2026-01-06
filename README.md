<h1>Html&CSS</h1>
This repo contains of notes I've taken during my learning html and css.
<hr>
<h3>The HTML Structure</h3>

```html
<!DOCTYPE html>
<html>
<head>
...
</head>
<body>
...
</body>
</html>
```
*In the head section --> things we don't see in the page. For example:
```html
<title>Title in the tab</title>                   <!--Sets the title in the tabs-->
<link rel="stylesheet" href="styles.css">         <!--Loads a CSS file to the page-->
```
<h3>CSS Structure</h3>
One way of writing CSS code is using the <style> HTML element.
<hr>

Creating links:  
```html
<a href="https://youtube.com" target="_blank">Link to YouTube</a>
```
*target="_blank" causes the link to be opened in a new tab.
<hr>

Class attribute(lets us target specific elements with CSS):
```html
<button class="subscribe-button">SUBSCRIBE</button>
```
```css
.subscribe-button {
...
}
```
*Multiple elements can have the same class

*An element can have multiple classes, separated by space:
```html
<button class="youtube-button subscribe-button">SUBSCRIBE</button>
```
*Attributes modify how an HTML element behaves.
<hr>

Buttons creating and styling:
```html
<button>Hello</button>     <!--Creates a button with the text "Hello" inside.-->
```
```css
<style>
button {
background-color: red;                               /*Sets the background color. Common values:
                                                                                ● Color name: red, white, black
                                                                                ● rgb value: rgb(0, 150, 255);
                                                                                ● Hex value: #0096FF*/

color: white;                                        /*Sets the text color. Takes the same values: color name, rgb, hex.*/
                                  
height: 36px;                                        /*Sets the height. Common values: ● Pixel value: 36px
                                                                                     ● Percentage: 50%*/

width: 105px;                                        /*Sets the width. Takes the same values as height.*/

border: none;                                        /*Removes the border.*/

border-radius: 2px;                                  /*Creates rounded corners.*/

cursor: pointer;                                     /*Changes the mouse/cursor when hovering over the element.*/

border-color: red;                                   /*Sets the border color.*/

border-style: solid;                                 /*Sets the border style. Common values: ● solid ● dotted ● dashed*/

border-width: 1px;                                   /*Sets the border width.*/
}

</style>
```
<hr>

CSS Pseudo-Classes:
```css
.subscribe-button:hover {                       /*These styles only apply when hovering over an element with class="subscribe-button"*/
...
}
.subscribe-button:active {                      /*These styles only apply when clicking on an element with class="subscribe-button"*/
...
}
```

<hr>

Intermediate CSS Properties:
```css
.subscribe-button {
opacity: 0.5;                                    /*Sets how see-through an element is: 0.5 = 50% see-through.*/
opacity: 0;                                      /*0 = complete see-through (invisible).*/
opacity: 1;                                      /*1 = not see-through (this is the default value).*/


transition: <property> <duration>;               /*Transition smoothly when changing styles (often used when hovering).*/

transition: background-color 1s;                 /*Transition background color over 1 second.*/
transition: color 0.15s;                         /*Transition text color over 0.15 seconds.*/

transition: <property1> <duration1>,             /*Transition multiple properties by separating them with a comma.*/
<property2> <duration2>,                          
...;

transition: background-color 0.15s,              /*Transition both background color and text color over 0.15 seconds.*/
color 0.15s;
                                
box-shadow: <h-position> <v-position> <blur> <color>;
box-shadow: 3px 4px 5px black;                   /*Creates a shadow that's 3px to the right of
                                                  the element, 4px to the bottom, with 5px of
                                                  blur, and color of black.*/

box-shadow: 3px 4px 0 rgba(0, 0, 0, 0.15);       /*Creates a shadow that's 3px to the right,
                                                  4px to the bottom, with no blur,
                                                  and a very faint black color.*/
}
```
<hr>

<h3>CSS Box Model</h3>

1. Margin = space on the outside 

2. Padding = space on the inside 

3. Border

```css
.join-button {

margin-right: 10px;                             /*Add 10px of space on the outside of the element.*/
margin-left: 10px;
margin-top: 10px;
margin-bottom: 10px;                            /*Normal margin pushes things away from an element.*/
margin-right: -20px;                            /*Negative margin pulls things towards an element like this*/

margin: 10px;                                   /*Shorthand for adding 10px of margin on all sides.*/
margin: 10px 20px;                              /*Add 10px of margin top & bottom and 20px left & right*/
margin: <top> <left & right> <bottom>;
margin: <top> <right> <bottom> <left>;

padding-right: 10px;                            /*Add 10px of space on the inside of the element.*/
padding-left: 10px;
padding-top: 10px;
padding-bottom: 10px;
padding-right: -20px;                           /*Negative padding has no effect.*/

padding: 10px;                                  /*Shorthand for adding 10px of padding on all sides.*/
padding: 10px 20px;                             /*Add 10px of padding top & bottom and 20px left & right*/
padding: <top> <left & right> <bottom>;
padding: <top> <right> <bottom> <left>;

border-width: 1px;                              /*Sets the border width.*/
border-style: solid;                            /*Sets the border style (to a solid color).*/
border-color: red;                              /*Sets the border color.*/
border: <width> <style> <color>;                /*Shorthand for the 3 properties above.*/
border: 1px solid red;
}
```
<hr>

Text(paragraph) creating and styling:
```html
<p>paragraph of text</p>   <!--Creates a paragraph of text.-->
```
```css
.title {
font-family: Arial;                              /*Change the font.*/
font-family: Roboto, Verdana, Arial;             /*A font-stack: if Roboto is not available, it will
                                                  fall back to Verdana. If Verdana is not
                                                  available it will fall back to Arial.*/
font-size: 30px;                                 /*Change text size.*/
font-weight: bold;                               /*Change text thickness.*/
font-weight: 700;                                /*Another way to specify font-weight. We can use: 100, 200,
                                                  300, ..., 900. bold = 700, regular = 400, semibold = 500*/

font-style: italic;
text-align: center;                              /*Other values we can use: left, right, justified*/
line-height: 24px;                               /*Adjust space between lines of text.*/
text-decoration: underline;                      /*Underlines the text.*/
text-decoration: none;                           /*Removes underline.*/
}
```
Text Elements (also called Inline Elements):

Text elements (strong, u, span, a) appear within a line of text. (Useful if we want to style only a part of the text.)
```html
<p>This is a <strong>text element</strong></p>
```
*We can style text elements using a class: (using span)
```html
<p>This is a <span class="shop-link">text element</span></p>
```
```css
.shop-link {
text-decoration: underline;
}
```
*Paragraph element by default have margin-top and margin-bottom. A common practice is to:
1. Reset the default margins.
```css
p {
margin-top: 0;
margin-bottom: 0;
}
```
2. Then apply more precise margins.
```css
.title {
margin-bottom: 16px;
}
```

Image creating and styling:
```html
<img src="image.png">   <!--Loads an image "image.png" beside the HTML file.-->
```
```css
.image {
width: 300px;                             /*Resizes the image to a width of 300px. Height will also
                                           resize to keep the image's dimensions.*/
height: 300px;                            /*If both width and height are set, the image may stretch.*/

object-fit: cover;                        /*Enlarges the image to cover the entire width * height area
                                           without stretching or distorting.*/
object-fit: contain;                      /*Shrinks the image so that it's contained in the width * height area.*/

object-position: left;                    /*Determines where the image is positioned in the width *height area.*/
object-position: right;
object-position: top;
object-position: bottom;
}
```

Inputs:
```html
<input type="text" placeholder="Search">       <!--Creates a text box and adds a placeholder (a label) to the text box.-->
<input type="checkbox">                        <!--Creates a checkbox.-->
```
```css
.search-bar {
font-size: 30px;                               /*Changes the font-size when typing into the text box.*/
}
.search-bar::placeholder { 
font-size: 30px;                               /*Changes the font-size of the placeholder.*/
}
```

CSS Display Property:
```css
.element {
display: block;                               /*Element will take up the entire line in its container.*/
display: inline-block;                        /*Element will only take up as much space as needed.*/
vertical-align: middle;                       /*Determines vertical alignment of inline-block elements.*/
display: inline;                              /*Element will appear within a line of text (a text element).*/
}
```

'div' element:
*'div' is a container. We generally put other elements (including other divs) inside. 'div's allow us to group elements together and create
more complex layouts.
```html
<div class="container">
  <p>Name</p>
  <input type="text">
</div>
<div class="container">
  <p>Quantity</p>
  <div>
    <button>1</button>
    <button>2</button>
  </div>
  <button>Submit</button>
</div>
```
```css
.container {
display: inline-block;
width: 200px;
}
```
Nested Layouts Technique:
There are 2 types of layouts:
1. Vertical Layout(=)
2. Horizontal Layout(||)

To Create the Vertical Layouts -->  

● Use 'div's with display: block (most common)                 

● Use flexbox with flex-direction: column                     

● Use CSS grid with 1 column

To Create the Horizontal Layouts --> 

● Use 'div's with display: inline-block (not recommended)     

● Use flexbox with flex-direction: row                        

● Use CSS grid with multiple columns

Inline CSS Styles:
Another way of writing css, using the style="..." attribute:
```html
<div style="
background-color: red;
color: white;
">
...
</div>
```
CSS Grid:
```css
.grid {
display: grid;                                 /*Turns an element into a grid container.*/
grid-template-columns: 100px 100px;            /*Sets how many columns are in the grid and how wide the columns are.*/
column-gap: 20px;                              /*Sets space between the columns.*/
row-gap: 40px;                                 /*Sets space between the rows.*/
}

.grid {
display: grid;
grid-template-columns: 100px 1fr;              /*1fr = the column will take up the remaining
                                                amount of space in the grid container.*/

grid-template-columns: 1fr 1fr;                /*The columns will take up an equal amount of the
                                                remaining space (since they're both 1fr).*/

grid-template-columns: 1fr 2fr;                /*The number in front of fr = relatively how much space the column gets.
                                                Here, the 2nd column gets twice the amount of space as the 1st.*/

justify-content: center;                       /*Aligns the columns horizontally in the center.*/
justify-content: space-between;                /*Spread out the columns evenly horizontally.*/

align-items: center;                           /*Aligns the columns vertically in the center.*/
}
```

Flexbox:
```css
.flexbox {
display: flex;                               /*Turns an element into a flexbox container.*/
flex-direction: row;                         /*Lays out elements horizontally inside the flexbox. Usually we don't need to
                                              specify flex-direction: row; because it is the default value.*/

justify-content: center;                     /*Centers the elements in the flexbox horizontally.*/
justify-content: space-between;              /*Spreads out the elements in the flexbox evenly across the horizontal space.*/

align-items: center;                         /*Centers the elements in the flexbox vertically.*/
align-items: space-between;                  /*Spreads out elements evenly in the vertical space.*/
} 
 
.element-inside-flexbox { 
width: 100px;                                /*Sets the width of the flexbox element to 100px.*/
flex: 1;                                     /*Take up the remaining amount of space. The value 1 determines relatively how much space.*/
flex-shrink: 0;                              /* *Don't shrink the element when resizing. Allow the element to shrink down when resizing.*/
width: 0;
}
```

```html
<div style="                                      
display: flex;                                     
flex-direction: row;                               
">
<!--Creates a flexbox where elements are placed horizontally (flex-direction: row; is the default so it's not mandatory to have that in the CSS)-->

<p style="width: 100px;">Flexbox element 1</p>      <!--This element has a width of 100px.-->

<p style="flex: 1;">Flexbox element 2</p>           <!--This element takes up 1/3 of the remaining space.-->

<p style="flex: 2;">Flexbox element 2</p>           <!--This element takes up 2/3 of the remaining space.-->
</div>
```
```css
.flexbox {
display: flex;                                   /*Lays out elements vertically inside the flexbox. */
flex-direction: column;                          /*Also, justify-content and align-items are reversed.*/
 
justify-content: center;                         /*Centers elements vertically inside the flexbox.*/
justify-content: space-between;                  /*Spreads out elements evenly in the vertical space.*/

align-items: center;                             /*Centers elements horizontally.*/
align-items: space-between;                      /*Spreads out elements evenly horizontally.*/
}   
```


CSS Position:

● Create elements that stick to the page while scrolling.

● Create elements that appear on top of other elements.

Position fixed:

```css
.element {
position: static;         /*This is the default value that every element starts with.*/
}
```

```css
.fixed {
position: fixed;                    /*Positions the element in the browser window (sticks to the page while scrolling).*/

top: 0;                             /*Places the element 0px from the top of the browser window.*/
bottom: 10px;                       /*10px from the bottom of the browser window.*/
left: 50px;                         /*50px from the left of the browser window.*/
right: 100px;                       /*100px from the right of the browser window.*/

top: -5px;                          /*Using negative pixels places the element beyond the top edge.*/

width: 100px;                       /*Sets the element's width to 100px.*/
height: 100px;                      /*Sets the element's height to 100px.*/
}

```
*If you set opposite directions (top/bottom or left/right), the element will stretch.

* When using width/height the element will not resize with
the page.
* When using top/bottom/left/right the element will resize
with the page.

Position Absolute:
```css
.absolute {
position: absolute;                           /*Positions the element on the page (it will scroll with the page and
                                                will not stick when scrolling).*/
top: 0;                                       /*Places the element 0px from the top of the page.*/
bottom: 10px;                                 /*10px from the bottom of the page.*/
left: 50px;                                   /*50px from the left of the page.*/
right: 100px;                                 /*100px from the right of the page.*/
width: 100px;                                 /*Sets the element's width to 100px.*/
height: 100px;                                /*Sets the element's height to 100px.*/
}
```
Position Absolute Inside Position Fixed:

● When a position: absolute element is inside a position: fixed element, it will be
positioned relative to the fixed element.

● This rule also applies to any position value that is not position: static.

● This lets us place elements in the corners of other elements. For example, a "Close"
button in the top-right corner

```html
<div style="
position: fixed;
width: 100px;
">
<button style="
position: absolute;                      
top: 0;
right: 0;
">
X
</button>
</div>
```
*The position absolute element will be placed in the top-right of the position fixed element.

Position Relative:
```css
.relative {
position: relative;                       /*The element will appear normally (as if it's position: static).
                                            We can then push it around with top/bottom/left/right.*/
top: 10px;                                /*Places the element 10px from the top of its original position(pushes it down by 10px).
                                            Unlike margin, it won't push the rest of the page down.*/
bottom: 10px;                             /*Places the element 10px from the bottom of its original position (pushes it up by 10px).*/

left: 50px;                               /*Places the element 50px from the left of its original position.*/
right: 100px;                             /*Places the element 100px from the right of its original position.*/
width: 100px;                             /*Sets the element's width to 100px.*/
height: 100px;                            /*Sets the element's height to 100px.*/
}
```

Position Absolute Inside Position Relative:

● When a position: absolute element is inside a position: relative element, it will
be positioned relative to the relative element.

● Useful if we want to display an element normally (using position: relative), but still
be able to place other elements in the corner (using position: absolute).

```html
<div style="
position: relative;
width: 100px;
">
<button style="
position: absolute;                 
top: 0;
right: 0;
">
3
</button>
</div>
```
*The position absolute element will be placed in the top-right of the position relative element


z-index:  Determines which elements appear in front and behind:

● Elements with a higher z-index appear in front of elements with a lower z-index. The
default z-index is 0.

● Elements with position: static; always appear at the back. z-index has no effect.

● If the z-index is equal or both elements are position: static, the element that was
written later in the code will appear in front.
```css
.fixed {
position: fixed;                        /*This element will appear in front of the position: absolute;
                                         element because it has a higher z-index.*/
z-index: 2;
}
.absolute {
position: absolute;
z-index: 1;
}
.static {
position: static;                      /*This element will appear at the back since it's                                                 position static.*/
}
```

Responsive Design:

Responsive design = making the website look good on any screen size.
```css
@media ( max-width : 750px ) {
  .element {
    width : 350px ;                                 
  }
}
/*Only apply the CSS code below when screen width is between 0px - 750px.*/

@media ( min-width : 750.02px ) and ( max-width : 1000px ) {
  .element {
    width : 450px ;
  }
}
/*Only apply this CSS code when screen width is between 750px - 1000px.*/

@media ( min-width : 1000.02px ) {
  .element {
    width : 600px ;
  }
}
/*Only apply this CSS code when the screen width is over 1000px.*/
```

Advanced CSS Selectors:
```css
/*With Comma*/
.class1 , .class2 { ... }             /*Target multiple classes at the same time.*/
.class1 , p { ... }                   /*Target a class and all <p> s at the same time.*/

/*With Space*/
.class1 img { ... }                   /*Target img's that are inside elements with
                                      class = "class1"*/                       
.class2 .tooltip { ... }              /*Target  .tooltip inside elements with class = "class2"*/

.class2:hover .tooltip { ... }        /*Target .tooltip only when hovering over elements with                                          class = "class2"*/
```
Inheritance:

A text property set on the outer element will be passed down into inner elements:
```html
<div style = "color: red;" >
  <p> Paragraph </p>
</div>
>!--This paragraph will have red text.-->
```
*For global text styles (styles we want on the entire page), we can set them on the body

CSS Specificity Rules:
1. Inline CSS has higher priority than .class selectors.
2. .class selectors have higher priority than element name selectors ( p ).
3. Element name selectors ( p ) have higher priority than inheritance (from body ).
4. If 2 selectors have the same priority, the one that is written later wins.



Semantic Elements:

Elements that work the same way as div . However, they also give the HTML meaning when
screen readers, search engines, or other devices read the website.
Common semantic elements include:  <i><b>header</b></i> , <i><b>nav</b></i>, <i><b>main</b></i> , <i><b>section</b></i> , etc.


Other CSS Properties:

```css
.tooltip {
  pointer-events : none ;        /*Disables all interactions with the mouse (clicks, hovers) */
  white-space : nowrap ;       /*Prevents the text inside the element from wrapping to
                              multiple lines.*/
}
```
