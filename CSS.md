# CSS

### Block Element : <h1>-<h6>, <p> , <div>
### Inline Element : <img>, <em>, <span>

### p : Selector
### font-family : Arial : Declaration
### font-family : Property
### Arial : Value
p {
  font-family: Arial;
}

External CSS => <link href="css/style.css" type="text/css" rel="stylesheet"
Internal CSS => <style type="text/css"> </style>

## CSS Selectors

Universal Selector : * {}
Type selector : h1, h2, h3 {}
Class Selector : .note {} ; p.note{} (p class="note")
ID selector : #introduction {}
Child Selector : li>a {} (<li><a href="zucchini.html"> Zucchini</a></li>)
Descendant Selector : p a {} => target <a> that is sit inside <p>, even if there are other elements nested between them
Adjacent Sibling Selector : h1+p {} => target the first <p> element after <h1> but not other elements nested between them
General sibling selector : h1~p{} => apply all <p> in the h1 elements.

!important : rules over everything

## CSS color
rgba(0,0,0,0.5)
hsla(0,0%,78%,0.5) h:Hue, s:Saturate, l:Lightness, a:Alpha or opacity

### CSS defines two types of gradients:
Linear Gradients (goes down/up/left/right/diagonally)
Radial Gradients (defined by their center)

background-image: linear-gradient(direction, color-stop1, color-stop2, ...)
background-image: linear-gradient(angle, color-stop1, color-stop2)

### Example:
background-image: linear-gradient(to right, rgba(255,0,0,0), rgba(255,0,0,1))
background-image: radial-gradient(red, yellow, green);
background-image: radial-gradient(circle, red, yellow, green);

## Text
Stretch : condensed , Regular, Extended
Style : Normal, Italic, Oblique
em : EMS equivalent to the width of a letter m

@font-face => allow to user font which are not installed in your computer
font-weight : normal, bold
font-style : normal, italic, oblique
text-transform : uppercase, lowercase, capitalize
text-decoration: underline, none, overline, line-through, blink
line-height : spacing between each text line  
letter-spacing : spacing within letter
word-spacing : spacing within words
text-align : left, right, center, justify
vertical-align : baseline, sub, super, top, tex-top, middle, bottom, tex-bottom (used with inline elements such as <img>,<em>, or<strong>)
text-indent : -10px, 10px, 3em (space before words)
text-shadow : 1px, 1px, 0px #666666 (can also be -1px feld like engrave)

:first-letter : as mentioned first letter of the <p>  => Exmaple:  p.intro:first-letter {font-size:200%}
:first-line : first line
### Styling links
:link : Example: a:linkkffr
:visited : Example a:visited
### Responding to users
:hover
:active
:focus

### Example:
a#framing-options:hover {}
a#add-to-basket:active {}

## Attribute Selectors
Existence [] => p[class] : target <p> element with an attribute called class
Equality [=] => p[class="dog"] : target any <p> element with attribute call class show value is dog
Space [~=] => p[class~="dog"]
Prefix [^=] => p[attr^"d"] : target any <p> element with attribute whose value begins with the letter "d"
Subtring [* =] => p[attr*"do"] : target any <p> element with attribute whose value with the letter "d"
Suffix [$=] => p[attr$"g"] : targes any <p> with an attribute whoes value ends with letter "g"

## BOX
width
height
min-width : min width when browser goes narrow
max-width : max width when browser goes broader
min-height
max-height
overflow : hidden (hides extra content when it is larger than box), scroll (add scrollbar to box when content is bigger than box)

## Border
border-width : thin, medium, thick or 2px 1px 1px 1px
border-top-width, border-right-width, border-bottom-width, border-left-width
border-style : solid, dashed, dotted, double, groove, ridge, inset(embedded), outset(coming out), hidden/none
border-top-style, border right-style, etc
border-color : border-top-color, etc
border-radius, border-top-right-radius, border-bottom-right-radius, etc : 100px (round), 1em 4em 1em 4em (odd and sketch square)

empty-cell : show, hide, inherit (choose what to do with empty cell  under table )
border-spacing: 5px 15px (spacing around border)
border-collapse: collapse (empty-cell does not work in this case), separate (provide auto spacing between borders)

### Example:
border: 3px dotted #0088dd

## Padding / Margin
padding, padding-top, padding-right, etc
margin, margin-top, margin-right, etc

### Example:
margin: 20px 10px (top & bottom 20px, right and left 10px )

## Centering Content
margin: 10px auto

## Positioning
### display
inline:
* cause block element to act inline and removed bullet
* respect left & right margins and padding, but not top & bottom
* cannot have a width and height set
* allow other elements to sit to their left and right.
* see very important side notes on this here.

block:
* respect all of those
* force a line break after the block element
* acquires full-width if width not defined

inline-block:
* allow other elements to sit to their left and right
* respect top & bottom margins and padding
* respect height and width

none : hides the element

### visibility
hidden: hides the element but still allocate the space for it
visible

border-image: url("images/dot.gif") 11 11 11 11 round (stretch, repeat, round)
box-shadow: Horizontal-Offset Vertical-offset Blur-distance Spread-of-shadow
both use -mox and -webkit infront of property to support Chrom, Firefox and Safari

## bullets (all setup in <ul>)
list-style-type: none, disc, circle, square, decimal, decimal-leading-zero, lower-alpha, upper-alpha, lower-roman, upper-roman
list-style-image: url("images/star.png")
list-style-position: outside (indent on the second line paragraph), inside (no indent space)
list-style: inside circle (two type style in one go )

### Cursor
cursor: auto, crosshair, default, pointer, move, text wait, help url("cursor.gif")

# Layout

## Position
static: normal flow (default)
relative:
absolute: taken out of normal flow and we can position with left, width, etc
fixed: fix the location even after screen scroll, it will appear on the screen fixed location

z-index: 10 (control position when relative, absolute and fixed overlap others)

clear: left, right, both, none (clearing specify location, usually use after float property)

### Fixed Width Layout : using px
### Liquid Layout : using em, % vw and vh

Screen layout : 960px wide; 12 column Grid

## Images
background-color
background-image: url("images/pattern.gif")
background-repeat: repeat-x (repeat horizontal), repeat-y (repeat vertical), no-repeat
background-attachment: fixed, scroll
background-position: left top / 50% 50%; (x-axis y-axis)

### Example:
background: #ffffff url("images/tulip.gif"> no-repeat top right;

## Flexbox

Notice that when the flex direction is a column, justify-content changes to the vertical and align-items to the horizontal.

`display: flex`
justify-content :  use for align top and bottom (changes to the vertical)
flex-start: Items align to the left side of the container.
flex-end: Items align to the right side of the container.
center: Items align at the center of the container.
space-between: Items display with equal spacing between them.
space-around: Items display with equal spacing around them.

align-items : use for align in line items(to the horizontal)
- flex-start: Items align to the top of the container.
- flex-end: Items align to the bottom of the container.
- center: Items align at the vertical center of the container.
- baseline: Items display at the baseline of the container.
- stretch: Items are stretched to fit the container.

align-self : use for individual item within a div. Sydntex same as align-items;

flex-direction:
row: Items are placed the same as the text direction.
row-reverse: Items are placed opposite to the text direction.
column: Items are placed top to bottom.
column-reverse: Items are placed bottom to top.

Oder : change the order within a div (order: 1, 2, 3 or -1, -2, -3)

flex-wrap:
nowrap: Every item is fit to a single line.
wrap: Items wrap around to additional lines.
wrap-reverse: Items wrap around to additional lines in reverse.

The two properties flex-direction and flex-wrap are used so often together that the shorthand property flex-flow was created to combine them. This shorthand property accepts the value of one of the two properties separated by a space.

flex-flow: row wrap / column wrap;
For example, you can use flex-flow: row wrap to set rows and wrap them


## Position
- static   = default
- relative => only effect on the specific item but not anything around it. Relative will have a origin reference point. Relative will find its place based on the html arrangement.
- absolute => disrupt entire environment. It will also reference to it's parents if they are in a div.
- fixed => fix the position as the body element.
