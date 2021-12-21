<h2> Turtle Module </h2>

<h4>Imagine a robotic turtle starting at (0, 0) in the x-y plane. After an import turtle, give it the command turtle.forward(200), and it moves (on-screen!) 200 pixels in the direction it is facing, drawing a line as it moves. Give it the command turtle.right(45), and it rotates in-place 45 degrees clockwise.By combining together these and similar commands, intricate shapes and pictures can easily be drawn.This is the concept we use in turtle module. </h4>

**Turtle Graphics**

```
import turtle
scrn = turtle.Screen()                  #creates a graphics window
sponge = turtle.Turtle()                #creates a turtle whose name is sponge
sponge.forward(200)                     #object.method(parameter)
sponge.left(90)                         #turn turtle left by angle units
sponge.forward(100)
sponge.right(90)                        #turn turtle right by angle units
sponge.forward(100)
sponge.left(90)
sponge.backward(30)
```

```
Just like we can have many different integers in a program, we can have many turtles.
Each of the turtle is an independent object and we call each one an instance of the Turtle type (class), Each instance has its own attributes and methods 
import turtle defines the module turtle which will allow you to create a Turtle object and draw with it.
turtle.Turtle; here "turtle" tells Python that we are referring to the turtle module, which is where the object "Turtle" is found
Geometry conventions have 0 degrees facing East and that is the case here too. 
Each instance can have attributes, sometimes called instance variables
sponge.forward(100) alex is an instance of the class Turtle.forward is a method.

``` 

**Creating a Rectangle**

```
import turtle                   #here loads a module named turtle
                                #This module brings two new types: the Turtle type, and the Screen type.
scrn = turtle.Screen()          #creates a graphics window
                                #scrn is an instance of Screen class
ciri = turtle.Turtle()          #means the Turtle type that is defined within the turtle module
                                #ciri is an instance of Turtle class
ciri.forward(180)               #object.method(parameter)
ciri.left(90)             
ciri.forward(75)         
ciri.left(90)
ciri.forward(180)
ciri.left(90)
ciri.forward(75)
```
**Creating  a triangle**

```
import turtle                  
scrn = turtle.Screen()         
mini = turtle.Turtle()
mini.forward(180)
mini.left(150)
mini.forward(100)      #object.method(parameter)
mini.left(60)
mini.forward(100)
```
**Creating rectangle and triangle together**

```
import turtle                  
scrn = turtle.Screen()         
ciri = turtle.Turtle()         
ciri.forward(180)           #object.method(parameter)
ciri.left(90)             
ciri.forward(75)         
ciri.left(90)
ciri.forward(180)
ciri.left(90)
ciri.forward(75)

mini = turtle.Turtle()
mini.forward(180)
mini.left(150)
mini.forward(100)      #object.method(parameter)
mini.left(60)
mini.forward(100)
```

**Using properties**

```
import turtle 
scrn = turtle.Screen()
scrn.bgcolor("lavender")
#the object scrn has color property(which we write as bgcolor)
arin = turtle.Turtle()
arin.color("blue")
arin.pensize(3)
#the object arin has property/attribute - color,pensize
arin.forward(100)
arin.right(90)                    #name.right(90) goes downward
arin.forward(90)

arina = turtle.Turtle()
arina.color("hot pink")
arin.pensize(4)
arina.forward(100)
arina.left(90)                    #name.left(90) goes upward
arina.forward(90)

#name.right(value)/name.left(value) works for defining angles(degrees).
```
**Mutliple objects with properties**

```
import turtle 
scrn = turtle.Screen()
scrn.bgcolor("lavender")
#the object scrn has color property(which we write as bgcolor)
arin = turtle.Turtle()
arin.color("blue")
arin.pensize(3)
#the object arin has property/attribute - color,pensize
arin.forward(100)
arin.right(90)                    
arin.forward(90)

arina = turtle.Turtle()
arina.color("hot pink")
arin.pensize(4)
arina.forward(100)
arina.left(90)                    
arina.forward(90)

ciri = turtle.Turtle()
ciri.color("yellow")
ciri.forward(180)           #object.method(parameter)
ciri.left(90)             
ciri.forward(75)         
ciri.left(90)
ciri.forward(180)
ciri.left(90)
ciri.forward(75)

mini = turtle.Turtle()
mini.forward(180)
mini.left(150)
mini.forward(100)      #object.method(parameter)
mini.left(60)
mini.forward(100)

prity = turtle.Turtle()
prity.color("green")
arin.pensize(2)
prity.right(45)
prity.forward(60)
prity.left(90)
prity.forward(100)

zina = turtle.Turtle()
zina.color("red")
zina.pensize(3)
zina.left(180)                   #notice this.it will make the line go in opposite direction
zina.forward(150)

scrn.exitonclick()                # wait for a user click on the canvas
#we invoke its exitonclick method of scrn object, the program pauses execution 
#and waits for the user to click the mouse somewhere in the window

```

**Using loops for repetitive patterns**

```
import turtle
scrn = turtle.Screen()
scrn.bgcolor("gray")
mim = turtle.Turtle()
mim.color("pink")
mim.pensize(3)
distance = 10
for i in range(20):
    mim.forward(distance)
    mim.right(90)
    distance = distance + 10

nim = turtle.Turtle()
nim.color("yellow")
nim.pensize(2)
distance = 9
angle = 90
for we in range(15):
    nim.forward(distance)
    nim.right(angle)
    distance = distance + 10
    angle = angle - 3

scrn.exitonclick()
```
**Using turtle shape method**

```
import turtle
scrn = turtle.Screen()
scrn.bgcolor("lavender")
xen = turtle.Turtle()
xen.color("blue")
xen.shape("turtle")

x = 5
xen.up()                     #Pull the pen up -- no drawing when moving
for i in range(50):
    xen.stamp()              #Stamp a copy of the turtleshape onto the canvas and return its id
    xen.forward(x)
    xen.right(25)
    x += 2

scrn.exitonclick()
```

**A design using turtle**

```
import turtle
scrn = turtle.Screen()
mini = turtle.Turtle()
mini.color("yellow")
mini.shape("turtle")
mini.penup()                     #picks the pen up so the turtle does not draw a line as it moves.
for i in range(10):
    mini.forward(50)
    mini.stamp()
    mini.forward(-50)
    mini.right(36)

    
scrn.exitonclick()
```
**Another design slighly changed condition from the previous one**

```
import turtle
scrn = turtle.Screen()
mini = turtle.Turtle()
mini.shape("turtle")
mini.color("pink")
mini.penup()                  #picks the pen up so the turtle does not draw a line as it moves.               
for i in range(10):
    mini.forward(50)
    mini.stamp()
    mini.right(36)
    mini.forward(-50)
   
    
scrn.exitonclick()
```
