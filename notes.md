Task given: Only use CSS to modify the website.

Helpful tip: 
    Use outline: 2px solid red; to show boxes.

Task 1: Centering the Product Card
    Horizontally centered on the page
    Balanced spacing

    Reference read:
    https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/margin?utm_source=chatgpt.com (Margin)
    - When one value is specified, it applies the same margin to all four sides.
    - When two values are specified, the first margin applies to the TB, the second to the LR.
    - When three values are specified, the first margin applies to the T, the second to the RL, the third to B.
    - When four values are specified, the margins apply (clockwise).

    Horizontal centering
    You can horizontally center an element within its parent by setting 
    
    margin: 0 auto;

    A more common method to center an element horizontally is by
    
    setting display: flex; and justify-content: center; 
     
    on a container, which centers its flex item children.

    So the basic syntax is:

    If html,
    <div class="center">This element is centered.</div>

    .center {
        margin: auto; -- since one argument, applies to all sides
        background: lime;
        width: 66%;
    }

    https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/max-width?utm_source=chatgpt.com (Max Width)

    The max-width CSS property sets the maximum width of an element.

    Prevents the used value of the width property from becoming larger than the value specified by max-width.

    #parent {
    background: lightblue;
    width: 300px;
    }

    #child {
    background: gold;
    width: 100%;
    max-width: 150px;
    }

    In this example, the "child" will be either 150 pixels wide or the width of the "parent," whichever is smaller.

    “This card may shrink on smaller screens, but it should not grow beyond this size.”

    https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Box_model?utm_source=chatgpt.com (Box Model)

    Everything in CSS has a box around it, and understanding these boxes is key to being able to create more complex layouts with CSS, or to align items with other items. 

    The CSS box model is just a way of thinking about the space around each element.

    Making up a block box in CSS we have the:

    Content box: The area where your content is displayed; size it using properties like width and height.
    
    Padding box: The padding sits around the content as white space; size it using padding and related properties.
    
    Border box: The border box wraps the content and any padding; size it using border and related properties.
    
    Margin box: The margin is the outermost layer, wrapping the content, padding, and border as whitespace between this box and other elements; size it using margin and related properties.

    What we want is specifically the padding box. So inside product-card for our case, you also set its padding.

Task 2: Use Flexbox
    https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Flexible_box_layout/Basic_concepts?utm_source=chatgpt.com 

    The flexible box layout module (usually referred to as flexbox) is a one-dimensional layout model for distributing space between items and includes numerous alignment capabilities.

    When working with flexbox you need to think in terms of two axes — the main axis and the cross axis. The main axis is defined by the flex-direction property, and the cross axis runs perpendicular to it.

    The main axis is defined by flex-direction, which has four possible values:
    row
    row-reverse
    column
    column-reverse

    Should you choose row or row-reverse, your main axis will run along the row in the inline direction. (horizontally)

    The cross axis runs perpendicular to the main axis. Therefore, if your flex-direction (main axis) is set to row or row-reverse the cross axis runs down the columns.

    Choose column or column-reverse and your main axis will run in the block direction, from the top of the page to the bottom. (vetically)

    If your main axis is column or column-reverse then the cross axis runs along the rows.

    If the flex-direction is row and I am working in English, then the start edge of the main axis will be on the left, the end edge on the right.

    An area of a document that is laid out using flexbox is called a flex container. To create a flex container, set the area's display property to flex.

    If single:
    border: 2px dotted rgb(96 139 168);
    display: flex;
    flex-direction: row-reverse;

    If multi-line:
    width: 500px;
    border: 2px dotted rgb(96 139 168);
    display: flex;
    flex-wrap: wrap;

    The align-items property aligns all the flex items on the cross axis. The initial value for this property is stretch and is why flex items stretch to the height of the flex container by default.

    You could instead set align-items to flex-start, or simply start, in order to make the items line up at the start of the flex container, flex-end, or just end, to align them to the end, or center to align them in the center.

    width: 500px;
    height: 130px;
    border: 2px dotted rgb(96 139 168);
    display: flex;
    align-items: flex-start;

Task 3: Improve Spacing
    https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/gap?utm_source=chatgpt.com 
    This is already kind of done with our previous iteration.

    Clear separation between sections should be focused.

    The gap CSS shorthand property sets the gaps (also called gutters) between rows and columns on multi-column, flex, and grid containers.

    gap = 
    <'row-gap'> <'column-gap'>?  

    #flexbox {
    display: flex;
    flex-wrap: wrap;
    width: 300px;
    gap: 20px 5px;
    }

Task 4: Style the Button Specifically
    Distinct color
    https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/background-color
    
    background-color: #FFA500;

    https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/border-radius
    Rounded corners
    The border-radius CSS shorthand property rounds the corners of an element's outer border edge.

    border-radius: 30px; (sets to all four)

    Logic execution (all, tl br, tl tr bl,  clockwise)

    https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/border
    Button Border Styling

    border: width style color;

    defaults to with border

Task 5: Add Hover Effect
    Button changes color on hover
    The :hover CSS pseudo-class matches an element when a user interacts with it using a pointing device. The pseudo-class is generally triggered when the user moves the cursor (mouse pointer) over an element without pressing the mouse button.
    
    a {
    background-color: powderblue;
    transition: background-color 0.5s;
    }

    a:hover {
    background-color: gold;
    }
    
    Transitions enable you to define the transition between two states of an element. Different states may be defined using pseudo-classes like :hover or :active or dynamically set using JavaScript.

    .target {
    font-size: 2rem;
    background-color: palegoldenrod;
    transition: background-color 2s 500ms;
    }

    transition: property duration timing-function;

    e.g. 
    transition: all 0.2s ease-in-out;

    all background color and size, 0.2s duration, animation

    Optional subtle scale transform
    https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Values/transform-function/scale?utm_source=chatgpt.com

    transform: scale(0.5); (scaleX and scaleY)

Task 6: Improve Typography
    Adjust font size hierarchy
    The CSS properties used to style text generally fall into two categories,

    Font styles: Properties that affect a text's font, e.g., which font gets applied, its size, and whether it's bold, italic, etc.
    
    Text layout styles: Properties that affect the spacing and other layout features of the text, allowing manipulation of, for example, the space between lines and letters, and how the text is aligned within the content box.

    The color property sets the color of the foreground content of the selected elements.

    color: red;

    To set a different font for your text, you use the font-family property — this allows you to specify a font (or list of fonts) for the browser to apply to the selected elements. 

    font-family: "Arial";

    sans-serif is of course the best

    Since you can't guarantee the availability of the fonts you want to use on your webpages (even a web font could fail for some reason), you can supply a font stack so that the browser has multiple fonts it can choose from.

    font-family: "Trebuchet MS", "Verdana", sans-serif;

    font-weight (bold)

    text-transform (case)

    text-decoration (mainly for links)

    text-shadow (shadow)

    text-align (justify)

    line-height (line spacing)

    word-spacing and letter-spacing (as you guessed)

    Make price visually dominant

Task 7: Make it Responsive
    https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Media_queries/Using

    Media queries allow you to apply CSS styles depending on a device's media type (such as print vs. screen) or other features or characteristics such as screen resolution or orientation, aspect ratio, browser viewport width or height, user preferences such as preferring reduced motion, data usage, or transparency.

    @media (max-width: 768px) {

    }

    then combine it with flex-direction column now

    @media (max-width: 768px) {
    .product-card {
        flex-direction: column;
    }
}
    basically says that you select the product card if the width is 768px