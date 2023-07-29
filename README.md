# CSS_Learning
This is to learn css

CSS - Cascading style sheet - A way to make HTML doc look good. 


# History of CSS development
CSSv1 - 1996
CSSv2 - 1998
CSSv3 - in development. Its split up into independent modules.

# CSS are of three types - 

## 1. Inline CSS. 
In which style attribute is added to each HTML tag and its style changed using properties:value for each property.

For ex - <H1 style="prop1:value; prop2:value; prop3:value and so on"> </H1>

In-line CSS can make the page difficult to manage and understand. So there is another way to use the same.

## 2. Internal CSS - 
In this, <style> </style> tag is used to put the rules in the head section of HTML page. Selectors are used to identify to which tag is this stle rule will be applicable. Selector are nothing but the HTML tag name with its body i.e html-tage-name{}. Body contains these rules - in the form -  property:value
Ex- <style>
    html-tag-name{
    prop1:value; prop2:value;
    } 
    </style>

Advantage of Internal CSS over the Inline CSS is that 
1. it helps disintegrate the CSS code from the HTML body. 
2. the same rule applicable to same tag, irrespective of the times it used in the html page.

Disadvantage of using Internal CSS is that it increases the size of the header. And for each new page reloaded on the browser, browser needs to fetch the header each time, which increases the browsing time.

## 3. External CSS -
In this style, CSS rules moved to the file. That file is only loaded onetime so increses the efficiency.
File is linked to the html page using link tag with rel attribute with stylesheet value and href attribute with file address value.
Ex- <link rel="stylesheet" href= "file-address">


# Google Font/Browser font-

Either we can use the fonts installed on the local system or we can use fonts from some website like google.
Fonts installed on system can be viewed in appearance tab under settings in chrome browser. Safari doesnt provide such feature to look.
To use the system installed font, we can select font-family to either standard, serif,sans-serif, fixed-width font, mathematic font.
To use th google font, we can go to the google font website, select the font which we want. Put the link mentioned in head section of the page and use the mentioned css rule in the css file.

# Different types of Selectors -
1. Element selector
2. Class selector (.)
3. id selector(#)
4. Universal selector(*)
5. Attribute selector([attribute])

## Element Selector -
This applies equal style for these elements.
Declared in css file as
Element-name{
    prop:value;
}
These applies to all elements on the HTML page.

## Class Selector -
This applies equal style to all elements with same class.
class is added to HTML element with class attribute.
Declared in css file as
.class-name{
    prop:value;
}
In HTML page-
<html-element class="class-name">

## Universal Selector -
To apply styles to all elements on the page. This is rarely used. But there are use-cases for this as well
Declared in css file as
*{
    prop:value;
}

## Id selector -
Each id is unique on a page. So this applies to one id only.
Declared in css file as
#{
    prop:value;
}

## Attribute selector
We select elements by their attributes. So multiple elements can have this style applied.
In CSS file -
[attribute-name]{
    prop:value;
}

# Cascading effect and Specificity
Same style rules can be applied to same HTML tag. So there are rules which determines what will be applied ultimately.
Order of the specificty from Highest to Lowest
Inline style
ID selector
class, pseudo-class, attribute selector
Tags and pseudo elemnet selectors

And if both are of same type, the one which appear later in the CSS file will get the priority and previous ones get overwiritten.

By looking into the inspect tool of the chrome browser under developer tools, we can easily find the 

Inheritance has lower priority. But is useful while passing styles down. Like using the styles in body and then it can be applied to all element which doesnt have any style applied.
Inheritance means an elements inherits some style from its parent element.

More specific rule has more specificity like in combinators


# C ombinators
## Adjacent Sibling Combinator
These are made by using + sign between the selectors we want to combine.
Ex - div + p 
All p which come within div get the same style.
Elements share the same parent.
Second element comes immediately after first parent.



## General Sibling Combinator
These uses ~ sign
Ex- div ~ p
ALl elements should be sibling.
All p which have div as sibling will get the same style.

## Child Combinator
These uses > sign
Ex - div > p
p should be direct child of div

## Descendant Combinator
These uses white space
Ex- div p
Its not necesssary to be direct child of parent. But p should be child of div direct or indirect.

# Useful Links -
Complete MDN CSS Reference (don't learn this by heart!): https://developer.mozilla.org/en-US/docs/Web/CSS/Reference

Do you prefer reading? Find written CSS docs on MDN: https://developer.mozilla.org/en-US/docs/Web/CSS

Common CSS Properties Reference: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Properties_Reference

CSS Combinators: https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Combinators_and_multiple_selectors

More details on CSS Specifity: https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity


# CSS Box Model
Every HTML element is considered as the block Like the following image
![Alternate image text](/Users/apple/css_learning/css box model.png)

There are 3 things with which a element is made of. And Marging is the area which surrounds the element.
Text area
Padding
Border 
Margin

Margin is the distance between the element and its sibling. Its not part of element.

There are two types of HTML elements -
1. Block level - which cover the complete width of the Page.These are rendered as box. Ex- h1 tag etc.
2. in Line - These elements cover only the width needed by the content. These are rendered as line Ex- Anchor tags
The behvaiour can be changed using dis[play property.
we can't set margin top and bottom. We can change the behaviour using display property.

display:inline/block/none/inline-block;
The display  Property: https://developer.mozilla.org/en-US/docs/Web/CSS/display

Compared to display: block, the major difference is that display: inline-block does not add a line-break after the element, so the element can sit next to other elements.

We had a look at display: none;  - this value removes the element to which you apply it from the document flow. This means that the element is not visible and it also doesn't "block its position". Other elements can (and will) take its place instead.

There is an alternative to that though.

If you only want to hide an element but you want to keep its place (i.e. other elements don't fill the empty spot), you can use visibility: hidden; 

Here's a visual example:

.box-1 {
    display: none;
}
 
.box-2 {
    display: inline-block;
}
Will render:

x  

where x  has the class box-2 . The first element just isn't displayed. It's still part of the DOM though, you can still access it via JavaScript for example.

Here's an example for visibility: hidden :

.box-1 {
    visibility: hidden;
}
 
.box-2 {
    display: inline-block;
}
Will render:

_x 

where _  simply is an empty spot and x  has the class box-2 .

The element is only invisible, it's not removed from the document flow and of course also not from the DOM.

CSS Box Model: https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Box_model

## Margin Collapsing
Bigger Marging wins.

Two elements each have the marging around it. If they are adjacents whichever element has the bigger margin wins the game.

But if this is annoying, they margin-top and margin-bottom can be used to get rid of these.

Dig deep here - https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing

There, three base cases are described:

Adjacent siblings which both have margins
A parent which holds one or more child elements where the first and/ or last (or the only) child has margins
An element without content, padding, border and height
Let's explore these cases:

1. Adjacent Siblings

In this case, the first element might have a margin of 10px  (on all sides let's say) and the second one has 5px  (or 20px  - the values don't matter).

CSS will collapse the margins and only add the bigger one between the elements. So if we got margins of 10px  and 5px , a 10px  margin would be added between the elements?

2. A parent with children that have a margin

To be precise, the first and/ or last or the only child has to have margins (top and/ or bottom). In that case, the parent elements margin will collapse with the child element(s)' margins. Again, the bigger margin wins and will be applied to the parent element.

If the parent element has padding, inline content (other than the child elements) or a border, this behavior should not occur, the child margin will instead be added to the content of the wrapping parent element.

3. An empty element with margins

This case probably doesn't occur that often but if you got an element with no content, no padding, no border and no height, then the top and bottom margin will be merged into one single margin. Again, the bigger one wins.

## SHort Hand Properties
These properties combines multiple properties in a single property.
Ex- 
1. 
border-width:20 px;
border-style: solid/ dasshed;
border-color: red;
 SHort-hand - border: 20px solid red; <--here order doesn't matter.-->

 2. 
 marging-top: 20px;
 margin-right:20px
 margin_bottom: 20px
 marging-left:20px
 Shorthand-  margin -20px

 ## Length and width
 Block level element take full 100% width by default.  So if we want to change the width, we can edit the width to some small % value.
 Length of element can also be given in percentage of the parent element. Sometimes, we don't see the change in the height of the element even when we edit the height of element to 100%. This happens because this percentage value is relative to the height of its parent. So in the tree, we need to go up till we set the desired height.
 More on height & width: https://www.w3schools.com/css/css_dimension.asp

 ### box-sizing
 content-box - height and width of the content is considered.
 border-box - height and width includes the border and the width.

 Box sizing, which doesn't include the margin. and browser automaticlly put the marging to the element. If we want to get rid of browser added things, we need to use the universal selector.
 *{
    box-sizing: border-box;
 }

 Note- inline-block level element occupy only the width needed by its elements. So we find difficulty in aligning the text sometimes, because they dont take the full block width. so we manually change the width to see the effect of alignment.

 box-sizing : https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing

 

## Pseudo classes and pseudo elements-
Pseudo classes defines the style of **specific state** of an element.
Defined with :class-name Ex- hower or active
.main-nav__item a:hover{
    color:white;
}
.main-nav__item a:hover{
    color:white;
}

WHen mouse cursor moves over the achor element of class main-nav__item, its(anchor block) color changes to white

Link to different pseudo classes-
MDN: https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes

Pseudo elements defines the style of **specific part** of element.
Defined with ::element-name
Ex- p::first-letter{
    color:red;
}
This will make first letter of paragraph red.

Link to different pseufo elements-
Elements: https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements

## Grouping
.main-nav__item a:hover{
    color:white;
}
.main-nav__item a:active{
    color:white;
}

can be grouped as

.main-nav__item a:hover,
.main-nav__item a:hover{
    color:white;
}

Similarly classes can also be grouped

## rounding corners

border-radius can be used to round the corner. for elliptic, two % values can be given. for circle, one single value is enough.

## url function to add the background image
url(path-to-image);

path-to-image can be hyper reference(i.e http address) or the local file.

# More on CSS Classes -
We can use more than one class wih one element.
Ex - <div class="class1 class2">  -- This uses more than one class.
Both classes can have independent rules.
.class1{
    property:value;
}
.class2{
    property:value;
}

Both classes have same specificity, order will not important here.

<a href="#" class="active">

a.active{  //here there is no white space between tag a and active class
    property:value;
}
a.active is written as one word. Targetting an element which is anchor tag and have the active class.
This can be appleied to more than one element i.e anchor tags

If we have a space between anchor tag and active call like a .active{}, then it will targetdirect or indirect descendant of anchor tag.(This will act as combinator). In similar line, we can define the id selector like a#active{}.

class selectors can be chained. like .priority.highlighted

## Id can be used for adding link to different sections of page.
so id are not just for styling purposes.
## !important notation
div{
    color:red !important  // This overwrites specifity and other selectors
}

In general: DOn't use the !important. Use specificty and rules to style your website a/q to your needs(and to write better CSS code in the end)

## :not pseudo class
This will allow to revert the property applied to a tag.
Ex- a:not(.active){

}
This will select any anchor tag which will not have active class.

But such selectors are performance sensitive. So always try to be simple which will enhance the performance.

## Browser support

A discussion on "classes vs IDs": https://stackoverflow.com/questions/12889362/difference-between-id-and-class-in-css-and-when-to-use-it
When is using !important  okay? => https://css-tricks.com/when-using-important-is-the-right-choice/
The :not()  pseudo class: https://developer.mozilla.org/en-US/docs/Web/CSS/:not
Can I Use: https://caniuse.com/

# Box shadow property
It allows you to define drop shadow or inset shadow by adding inset as first keyword and then adding same parameters. The other values are positioning of shadow on x-axis, y-axis, blurinesh and the spread(spread beyond the border) and the shadow color.

# color function
rgb(r,g,b)
rgb(r,g,b, alpha) -- alpha channel defines the transparency. value in 0 to 1.

# cursor property
value - pointer to make the hand shape when you hover over the button tag etc.

# outline
outline is not part of the box but is something which comes just after border and just before margin.
It can be set by browser. So first inspect it the developer tool. and then remove by using pseudo class.

# margn auto
It will center the element horizontally. It will fill space left and right equally.

# text-decoration
to remove the underlining of text etc

# float and clear
float property float the elements left or right of the document flow. It will float around the text. So it will affect the adjacent elements.
It looks like it is taking out the element out of the document flow.

To fix this issue, we can use another element with poperty clear:both to clear the floating effect on both side of this element. This hack is useful when we wanto to avoid the text of the next element(and its position) get affected by its previous element.

More on float: https://developer.mozilla.org/en-US/docs/Web/CSS/float

# Position Property
This property helps position the elements on the HTML page.
By default, position = static, which keeps the element in the HTML document flow.

Other values of position can be 
1. Fixed 2. Absolute 3. Relative 4. sticky

If position != static, then element can be taken out of document flow.
Position of an element can be changed into 4 directions-
1. top 2. right 3. left 4. bottom


## position = fixed;
With this, element is taken out of the HTML document flow. Element start behaving as the inline-box. Now it can be moved in all directions.

There is another direction called z-index  which helps in moving the element in z direction i.e perpendicular to the screen. The + value will bring the element to the top and negative values will take the element down. The auto value or zero value will not change the position of element.

top = 10px;
left = 20px;
right=20px;
bottom=20px;
Here position context is view port

## position = absolute
Position of elemnet to which this property applies depends upon two rules
1. if none of the ancestors of parent elements have poistion property applied, then the position context of the element is the html 
element.

2. if some of ancestors have the position property applied, then closest ancestor which has position property applied is the position context of the element.
## position = relative


## position = sticky


## stacking concept



