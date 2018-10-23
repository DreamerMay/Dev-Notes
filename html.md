# Tags

<sup> : raising (4<sup>th</sup>)
<sub> : foot notes (CO<sub>2</sub>)

<be /> : line break
<hr /> : add horizontal rule between section

<b> / <strong> : strong and bold
<i> / <em> : italic

<blockquote> : usually use on longer quotes
<q> : represent " "

<acronym title="National Aeronautics and Space Administration"> NASA </acronym> : when hover NASA the full name show
<cite> : for reference of book, film or research paper. Element within it will be italic
<dfn>
<address> ; italic and show address

<del> : delete or cross the Element
<ins> : show content with underline
<s> : something no longer accurate or relevant (same as cross)

<ol> : ordered list
<ul> : unordred list
<li> : list (after <ol> it will show number) ; list (after <ul> it will show bullets)

## Definition List
<dl> : create series of dt and dd inside this element
<dt> : term being defined
<dd> : contain the definition

## link
Absolute URL : <a href="http://www">
Relative URL<a href="index.html">
../ : return to one folder above
../../ : return to 2 folder above

<a href="mailto:jon@exampe.org"> Email Jon </a>
<target = "_ blank"> : will not change the current page but open new tab or new page.

Link to a specific part of same pages
### Example:
<h1 id="top"> : Create an ID for a specific location as an anchor
<a href="#arc_shot"> Arc Shot </a>
<a href="#interlude"> Arc Shot </a>
<a href="#prologue"> Arc Shot </a>
<h2 id="interlude"> Interlude </h2>
<h2 id="prologue"> Interlude</h2>

<p><a href="#top">Top</a> </p>

## Adding image
<img src="images/quokka.jpg" alt=" A family of quokka" title="The quokka is an Australia" width="600" height="450"/>

## Image location and alignment
Block Element = appear on a new line
Inline Element = sit within a block level element and do not start on a new line
### Example:
<figure>
  <img src="images/otter.jpg" alt="test"/>
  <figcaption> Description of photo. </figcaption>
</figure>

## Table
<table> : create a Table
<tr> : start of row
<tb> : each cell
<th> : like <td> but it represent heading for column or row

### Example:
<table>
  <tr>
    <td>15</td>
    <td>15</td>
    <td>30</td>
  </tr>                   RESULT :
  <tr>                              15 15 30
    <td>45</td>                     45 60 45
    <td>60</td>                     60 90 90
    <td>45</td>
  </tr>    
  <tr>
    <td>60</td>
    <td>90</td>
    <td>90</td>
  </tr>    
  <tr>
    <th></th>  : this represent the first cell (empty in this case)
    <th scope="col">Saturday</th>
    <th scope="col">Sunday</th>
  </tr>
  <tr>                                        RESULT :
    <th scope="row">Tickets Sold: </th>                     Saturday  Sunday
    <td>230</td>                              Tickets Sold: 120       135
    <td>135</td>                              Total Sale:   EVERYTHING
  </tr>
  <tr>
    <th scope="row">Total Sale:</th>
    <td colspan="2"> EVERYTHING </td> : take two space of column
    <td rowspan="2"> EVERYTHING </td> : take two space of row
</table>

## Long table
Tag segment with  :
<thead> : Header of the table
<tbody> : data list of the table
<tfoot> : total or sum at the end of the table

# FORM
<form>
action : every form requires an action attribute. Value of URL for page on theserver that will receive the info in the form to submit
method : GET or POST
id : the value is used to identify the form distinctly from other elements on the page
size : used for old forms only to indicate width of text input
### Example:
<form action="http://www.example.con/subscription.php" method="get">

<input> : element used for user input
type = "text" : let user enter text
type = "password" : display dots instead of text or numbers
type = "radio" : display as round with dot options
type = "checkbox" : dipaly as checkbox options
name : for server to know which form control each piece of data ws entered
maxlenght : max length limit
checked : indicated options being checked or tick
### Example:
<input type="text" name="username" size="15" maxlength="30" />
<input type="radio" name="genre" value="pop" checked="checked" /> Pop
### Example:
<textarea> : let user input paragraph of text
<textarea name="comments" cols="20" rows="4"> Enter your coments</textarea>

## Drop down list
<Select> : select box
name : name attribute indicate name of the form
value: value attribute which will send to server
selected : selected item
multiple : provide user for multiple options
size : qty of the value show at once (which include first on as ZERO)
### Example:
<select name="device" multiple="multiple">
  <option value ="ipod" selected="selected">iPod</option>
  <option value ="Radio">Radio</option>
  <option value ="Computer" selected="selected">Computer</option>
</select>

## File input box
type = "file" : create Browse button and text input
type = "submit" : create submit button to send to server
type = "image" : use image as submit button instead
<button> :
type = "hidden" : hidden from user but still able to capture info required when user submit

### Example:
<input type="file" name="user-song"/>
<input type="submit" value ="Upload"/>
<input type="submit" name="email" value ="Subscribe"/>
<input type="image" src="images/subscribe.jpg" width="100" height="20"/>

<button><img src="image/add.gif" alt ="add" width="10" height="10"/> Add </button>
<input type="hidden" name="bookmark" value="lyrics"/>

## Label
<label> : wrap around both text description and form input / kept seperate from the form control and use for attribute
for :  control the Labels belong to (where the input id are the same name as the for input )
### Example:
<label> Age: <input type="text" name="age" /></label>
<input id="female" type="radio" name="gender" value="f">
<label for="female">Female</label>

## Group form elements
<fieldset> :use for long forms
<legend> : come directly after <fieldset> containts name of the confrol group form

### Example:
<fieldset>
  <legend>Contact details </legend>
  <label>Email:<br />
  <input type="text" name="email" /></label><br />
  <label>Mobile:<br />
  <input type="text" name="mobile" /></label<br />
  <label>Telephone: <br />
  <input type="text" name="telephone" /></label>
</fieldset>

## Form Validation
required = "required" : add validation in the form
type = "date" : under input type, will include date browser.
type = "email" : only accept email format
type = "url"
type = "search"
placeholder : text advice user what to key-in

### Example:
<form action="http://www.example.org/profile.php">
  <p>Please enter your website address:</p>
    <input type="date" name="depart" />
    <input type="email" name="email" />
    <input type="url" name="website" />
    <input type="submit" value="Submit" />

  <p>Search:</p>
    <input type="search" name="search" placeholder="Enter Keyword"/>
    <input type="submit" value="Search" />
</form>

## Extra Markup

<iframe
  src="http://maps.google.co.ul/maps?q=moma+new+york&amp;output=embed"
  width="450"
  height="250"
  frameborder="0"
  scrolling="no">
</iframe>

<meta> : information contain inside specific Tag
<head>
  <title> Information About Your Pages</title>
  <meta name="description" content="An essay on installation Art" />
</head>

## Adding movies
Choice : preload, none, auto, metadata
poster : image to show before video is downloading

### Example:
<video src="video/puppy.mp4"
  poster="images/puppy.jpg"
  width="400" height="300"
  preload
  controllers
  loop>
  <p> A video of a puppy playing in the snow</p>
</video>

<video poster="images/puppy.jpg" width="400" height="320" preload controls loop>
  <source src="video/puppy.mp4" type='video/mp4;codec="avc1.42E01E, mp4a.40.20"' />
</video>

## Adding audio
controls : create audio player on screen
autoplay : auto play the sound once it's loaded

<audio controls autoplay>
  <source src="audio/test-audio.mp3" />
</audio>

## HTML Layout
<header>
<nav>
<article> => act as Content
<aside> => side bar or side content
  <secton> => related to content, typically each section would have its own heading
  <hgroup> => group together a set of one or more <h1> through <h6> so they are treated as single heading
<footer>

### Example:
<header>
  <h1> XXX </h1>
  <nav>
    <ul>
      <li><a href="" class="current">home</a></li>
      <li><a href=""> classes</a></li>
      <li><a href=""> catering</a></li>
      <li><a href=""> about</a></li>
      <li><a href=""> contacts</a></li>

    </ul>
  </nav>
</header>

<article>
  <figure>
    <figcaption> xxx </figcaption>
  </figure>
  <hgroup>
    <h2> XXX <h2>
  </hgroup>
  <p> Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
</article>

<footer>
  &copy: 2011 Sherine
</footer>
