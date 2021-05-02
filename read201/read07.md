# Tables

**What's a Table?**


>A table represents information in a grid format. 
Examples of tables include financial reports, TV 
schedules, and sports results
A table represents information in a grid format. 
: definition

------------------------

>Basic Table Structure
> 1. `<table>`
> The <table> element is used 
to create a table. The contents 
of the table are written out row 
by row
2. `<tr>`
 >You indicate the start of each 
row using the opening `<tr>` tag. 
(The tr stands for table row.) 
It is followed by one or more `<td> `elements (one for each cell in that row). At the end of the row you use a closing `</tr>` tag

3. `<td>`
 > `Each cell of a table is 
represented using a <td>
element. (The td stands for 
table data.)`

------------------------

> Table Headings
> `<th>`
>  1. The `<th> `element is used just 
like the` <td>` element but its 
purpose is to represent the 
heading for either a column or 
a row. (The th stands for table 
heading.) 

![img](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTT7yWAVbDWrJw7wXk1g-uU2xUXlmLRvQ7nWw&usqp=CAU)

---------------
*Old Code:
Width & Spacing*
> There are some outdated 
attributes which you should not 
use on new websites. You may, 
however, come across some 
of them when looking at older 
code, so I will mention them 
here. All of these attributes have 
been replaced by the use of CSS
-----------


### CREATING OBJECTS USING CONSTRUCTOR SYNTAX 
>On the right, an empty object 
called hote 1 is created using the 
constructor function. 
Once it has been created, three 
properties and a method are 
then assigned to the object. 
(If the object already had any 
of these properties, this would 
overwrite the values in those 
properties.) 
To access a property of this 
object, you can use dot notation, 
just as you can with any object. 
For example, to get the hotel's 
name you could use: 
hotel .name 
Similarly, to use the method, 
you can use the object name 
followed by the method name: 
hotel.checkAvailability() 
e FUNCTIONS, METHODS & OBJECTS 
`c3/js/object-constructor.js 
var hotel = new Object(); 
hotel.name= 'Park'; 
hotel.rooms = 120; 
hotel .booked = 77; 
hotel .checkAvailability = function() 
return this.rooms - this.booked; 
} ; 
JAVASCRIPT 
var elName = document.getElementByid('hotelName'); 
elName.textContent = hotel . name; 
var elRooms = document .getElementByid('rooms'); 
elRooms.textContent = hotel .checkAvailability(}; `


> ADDING AND REMOVING 
PROPERTIES 
*Once you have created an object 
(using literal or constructor 
notation), you can add new 
properties to it. 
You do this using the dot 
notation that you saw for adding 
properties to objects on pl03. 
In this example, you can see that 
an instance of the hotel object 
is created using an object literal. *

--------------------------

###### The first thing you need to do is get to know what tools are available. 
You can imagine that your new toolkit has three compartments:

--------------------
1. BROWSER OBJECT MODEL 
The Browser Object Model contains 
objects that represent the current 
browser window or tab. It contains 
objects that model things like 
browser history and the 
device's screen. 

2. BROWSER OBJECT 
MODEL 
The Browser Object Model contains 
objects that represent the current 
browser window or tab. It contains 
objects that model things like 
browser history and the 
device's screen. 

3. BROWSER OBJECT 
MODEL 
The Browser Object Model contains 
objects that represent the current 
browser window or tab. It contains 
objects that model things like 
browser history and the 
device's screen. 