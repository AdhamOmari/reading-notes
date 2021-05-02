## WHAT IS AN OBJECT?
> Objects group together a set of variables and functions to create a model of a something you would recognize from the real world. In an object, 
variables and functions take on new names.

 IN AN OBJECT: VARIABLES BECOME 
KNOWN AS PROPERTIES 
-------------------
![img](https://res.cloudinary.com/practicaldev/image/fetch/s--rJeH0yGE--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://thepracticaldev.s3.amazonaws.com/i/t52ni02srb8688lh3eh8.png)
---------

##  Document Object Model (DOM)
> specifies 
how browsers should create a model of an HTML 
page and how JavaScript can access and update the 
contents of a web page while it is in the browser window. 


> **THE DOM TREE IS A 
MODEL OF A WEB PAGE**
> **As a browser loads a web page, it creates a model of that page. 
The model is called a DOM tree, and it is stored in the browsers' memory. 
It consists of four main types of nodes.**
---------------

> **Each node is an object with methods and properties.**

![img](https://res.cloudinary.com/practicaldev/image/fetch/s--B2Ts1hyb--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/http://i67.tinypic.com/2nqegt2.jpg)

**WORKING WITH THE DOM TREE**
> 1. STEP 1: ACCESS THE ELEMENTS 
> 2. WORK W ITH THOSE ELEMENTS


> METHODS THAT RETURN A SINGLE ELEMENT NODE: 
> 1. getElementByld( id )
> 2. querySel ector(css selector') 

###### METHODS THAT RETURN ONE OR MORE ELEMENTS (AS A NODELIST)

> 1. METHODS THAT RETURN ONE OR MORE ELEMENTS (AS A NODELIST)
> 2. getEl ementsByTagName( tagName )
> 3. querySelectorAll 



# *SELECTING ELEMENTS USING ID ATTRIBUTES*
> *get El ementByi d () allows you 
to select a single element node 
by specifying the value of its 
id attribute. 
This method has one parameter: 
the value of the id attribute on 
the element you want to select. 
This value is placed inside quote 
marks because it is a string. The 
quotes can be single or double 
quotes, but they must match. 
In the example on the left, the 
first line of JavaScript code finds 
the element whose id attribute 
has a value of one, and stores 
a reference to that node in a 
variable called e 1.*


**SELECTING AN ELEMENT 
FROM A NODELIST**

> *There are two ways to select an element from a Nodelist: 
The item() method and array syntax. 
Both require the index number of the element you want.*
> 1. THE item () METHOD



###### LOOPING THROUGH A NODELIST
-------------------

![img](https://www.codegrepper.com/codeimages/loop-through-html-nodelist.png)


#### TRAVERSING THE DOM 
1. **parentNode**
2. **previousSiblingnextSibling**
3. **firstChildlastChild**


![img]()