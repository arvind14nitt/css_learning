# css_learning
This is to learn css

CSS - Cascading style sheet - A way to make HTML doc look good. 

# History of CSS development
CSSv1 - 1996
CSSv2 - 1998
CSSv3 - in development. Its split up into independent modules.

# CSS are of three types - 

## 1. inline CSS. 
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