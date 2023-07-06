# css_learning
This is to learn css

CSS - Cascading style sheet - A way to make HTML doc look good. 

CSSv1 - 1996
CSSv2 - 1998
CSSv3 - in development. Its split up into independent modules.

CSS are of three types - 

1. inline CSS. In which style attribute is added to each HTML tag and its style changed using properties:value for each property.

For ex - <H1 style="prop1:value; prop2:value; prop3:value and so on"> </H1>

In-line CSS can make the page difficult to manage and understand. So there is another way to use the same.

2. Internal CSS - In this, <style> </style> tag is used to put the rules in the head section of HTML page. Selectors are used to identify to which tag is this stle rule will be applicable. Selector are nothing but the HTML tag name with its body i.e html-tage-name{}. Body contains these rules - in the form -  property:value
Ex- <style>
    html-tag-name{
    prop1:value; prop2:value;
    } 
    </style>

Advantage of Internal CSS over the Inline CSS is that 
1. it helps disintegrate the CSS code from the HTML body. 
2. the same rule applicable to same tag, irrespective of the times it used in the html page.

Disadvantage of using Internal CSS is that it increases the size of the header. And for each new page reloaded on the browser, browser needs to fetch the header each time, which increases the browsing time.

3. External CSS - In this style, CSS rules moved to the different file. That file is only loaded onetime so increses the efficiency.