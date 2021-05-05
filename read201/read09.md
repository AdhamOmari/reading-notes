# Forms
> *The best known form on the web is probably 
the search box that sits right in the middle of 
Google's homepage*


###### How Forms Work
1. A user fills in a form and then presses a button 
to submit the information to the server.
2. A user fills in a form and then presses a button 
to submit the information to the server.
3. A user fills in a form and then presses a button 
to submit the information to the server.
4. A user fills in a form and then presses a button 
to submit the information to the server.

![alt](https://img.webnots.com/2014/01/How-HTML-Form-Works.png)


-----------------------

##### Form Structure
- `<form>`
- `action`
- `method`
- `id`
- ----------------
### **Text Input**
>`<input>`
The `<input>` element is used 
to create several different form 
controls. The value of the type
attribute determines what kind 
of input they will be creating.

>`type="text"`
When the type attribute has a 
value of text, it creates a singleline text input.

>`name`
When users enter information 
into a form, the server needs to 
know which form control each 
piece of data was entered into. 
(For example, in a login form, the 
server needs to know what has 
been entered as the username 
and what has been given as the 
password.) Therefore, each form 
control requires a name attribute. 
The value of this attribute 
identifies the form control and is 
sent along with the information 
they enter to the server.

> `maxlength`
You can use the maxlength
attribute to limit the number 
of characters a user may enter 
into the text field. Its value is the 
number of characters they may 
enter. For example, if you were 
asking for a year, the maxlength
attribute could have a value of 4.

---------------

**Lists,Tables and Forms**

![alt](https://blog.hyperiondev.com/wp-content/uploads/2018/11/HTML-Tut-2-10-Linking-Images.jpg)


### Positioning the Marker
> list-style-position
Lists are indented into the page 
by default and the list-styleposition property indicates 
whether the marker should 
appear on the inside or the 
outside of the box containing the 
main points.

> This property can take one of 
>two values:
>1. outside
>2. inside
------------------------------

##### Gaps Between Cells
###### border-spacing, border-collapse

>The border-spacing property 
allows you to control the 
distance between adjacent cells. 
By default, browsers often leave 
a small gap between each table 
cell, so if you want to increase 
or decrease this space then 
the border-spacing property 
allows you to control the gap.
The value of this property is 
usually specified in pixels. You 
can specify two values if desired 
to specify separate numbers for 
horizontal and vertical spacing.
When a border has been used 
on table cells, where two cells 
meet, the width of lines would be 
twice that of the outside edges. 
It is possible to collapse adjacent 
borders to prevent this using the 
border-collapse property. 
Possible values are:

>1. collapse
Borders are collapsed into a 
single border where possible. 
(border-spacing will be 
ignored and cells pushed 
together, and empty-cells
properties will be ignored.)

>2. separate
Borders are detached from each 
other. (border-spacing and 
empty-cells will be obeyed.)

---------------------

----------
### When you browse the web, your browser registers different types of events. It's the browser's way of saying, "Hey, this just happened." Your script can then respond to these events

>INTERACTIONS EVENTS TRIGGER CODE RESPONDS 
CREATE EVENTS CODE TO USERS 
Events occur when users When an event occurs, In the last chapter, you 
click or tap on a link, hover or fires, it can be used saw how the DOM can 
or swipe over an element, to trigger a particular be used to update a page. 
t ype on the keyboard, function. Different code The events can trigger the 
resize the window, or can be triggered when -kinds of changes the DOM 
when the page they users interact with is capable of. This is how a 
requested has loaded. different parts of the page. web page reacts to users.

![alt](https://data-flair.training/blogs/wp-content/uploads/sites/2/2019/07/JavaScript-Event-Types.jpg)