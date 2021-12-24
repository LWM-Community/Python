# OOP ( Object Oriented Programming) 
Requirement: List, Dictionary , Function etc


So, OOP is basically programming with Object
So, What is Object? To know this, you have to know what is Class? 
Okay , do know about string? Let's see what are there in the directory of string

```
print(dir(str))
```
Output:

```
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isascii', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'removeprefix', 'removesuffix', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']

```
so, what are they? There are methods under "str" class
for example: upper is a method and __doc__ is a private method
and method is mainly function within a class . Nothing else!

So , you have a little knowledge of "class" now

Let's create a class named example :

```
class example:
    print("Congratulations! you have created your first class")

```
Output:

```
Congratulations! you have created your first class
```
now we will create method within the class and remember that, while you create the method, you will have to give "self" parameter 

```
class example:
    def hello_world(self):
        print("Created 1st method")
```
now the question is that what is self? this self is basically to differ from other class . But to know about this, you need to know what is object. You may consider object/instance as a child of a class. Let's create a class:

```
class example1:
    def hello_world(self):
        print("Created 1st method")


object=example1()# created an object
```
To use the class, you just need  to create an object with the class name and you can then use all the method and variable within the class. Let's create an object and use it.

```
class example1:
      def hello_world(self):
          print("Hello world")

      def details(self):
          print("We are learning OOP")

object1=example1()
object1.details()#using details method

```
Output:

```
We are learning OOP
```
Here we have created an object and used details method of the class through the object

Now let's assume , you want to give some input and then work depending on those input, you can use __init__ method for that . Basically __init__ method is made to do must things of a class

```
class example1:
    def __init__(self):
        print("Hey! used the __init__ method")

    def hello_world(self):
          print("Hello world")

    def details(self):
          print("We are learning OOP")

object1=example1()


```

Output:

```
Hey! used the __init__ method
```
So, look here we created an object but did not call any method , still this is printed . The reason is that, we have added that under __init__ . so these sort of things are done using __init__
.

Now, let's take some input while creating an object and use them .

```
class example1:
    def __init__(self,name, country):

        self.variable_1=name
        self.variable_2=country
        print(self.variable_1)
        print(self.variable_2)

object1=example1("Mitul", 'Bangladesh')
```
here, while creating the object we are taking 2 values. Name and country name. and then look def __init__(self,name, country) here, we have set 3 parameter. self,name and country . Self is a must but other 2 are taken for 2 input we will take while creating an object. 

```
class example1:
    def __init__(self,name, country):

        self.variable_1=name
        self.variable_2=country
        print(self.variable_1)
        print(self.variable_2)
        print("-----------")

object1=example1("Mitul", 'Bangladesh')
object2=example1('Karim', "India")
```
Now , you can see that we have 2 objects now and we can use as many time as we want providing name and country 
Output:

```
Mitul
Bangladesh
-----------
Karim
India
-----------
```
You can again provide default values for variables within __init__

```
class example1:
    def __init__(self,name, country="default"):

        self.variable_1=name
        self.variable_2=country
        print(self.variable_1)
        print(self.variable_2)
        print("-----------")

object1=example1("Mitul")
```
Output:

```
Mitul
default
-----------
```
Now, let's know more about self using 2 class 

```
#class 1
class Hospital:
    def __init__(self,name):
           self.name=name
           self.d_dict={}
           self.p_dict={}
           self.d_count=0
           self.p_count=0

    def addDoctor(self,var):
        self.d_dict[var.d_id]=[var.d_name,var.d_spe]
        self.d_count+=1


    def getDoctorByID(self,val):
        if val in self.d_dict.keys():
            return f"Doctor's ID:{val}\nName:{self.d_dict[val][0]}\nSpeciality:{self.d_dict[val][1]}"


    def allDoctors(self):
        print("All Doctors")
        print(f"Number of Doctors: {self.d_count}")
        print(self.d_dict)

#class 2
class Doctor:
    def __init__(self,id,occ,name,spe):
        self.d_id=id
        self.d_occ=occ
        self.d_name=name
        self.d_spe=spe



h = Hospital("Evercare")# created an object with hospital name and Hospital class
d1 = Doctor("1d","Doctor", "Samar Kumar", "Neurologist") #created an object with Doctor class and with id, occupation , name , speciality 
h.addDoctor(d1) #used a method of Hospital class . Notice h is not an object under Doctor class but addDoctor is under the class Doctor. So, we are basically using a method called addDoctor with an object not created from his own class

print(h.getDoctorByID("1d"))

```

Output:

```
Doctor's ID:1d
Name:Samar Kumar
Speciality:Neurologist
```
So, don't think about the code. Here we created "h" object through Hospital class and "d1" through Doctor class . so we used "getDoctorById" method  through the object "h" and here into the code, while we used this:

```
    def addDoctor(self,var):
        self.d_dict[var.d_id]=[var.d_name,var.d_spe]
        self.d_count+=1
```
if you check the line self.d_dict[var.d_id]=[var.d_name,var.d_spe] here, var refers to object of other class or in a word this is of a different class but self refers here things of only Hospital class. so , self here differs between 2 class . 

So, stay cool. Don't need to panic if you don't realize anything.


Let's learn things gradually to master OOP


**Public, Protected & Private Variable**
Public variable : It can be used outside the class and in other class too

```
class Car:
    numberOfWheels=4

class Bmw(Car):
    def __init__(self):
        print("Inside the BMW Class",self.numberOfWheels)

car=Car()
print(car.numberOfWheels)#used outside of the class
bmw=Bmw()
```
Output:

```
4
Inside the BMW Class 4
```

Protected Variable: This variable can be used in other class and also outside of the class but you need to use "_" to create this sort of variable 

```
class Car:
    _color = "Black" #proteced variable

class Bmw(Car):
    def __init__(self):
        print("Inside the BMW Class",self._color)#used within a different class

car=Car()
print(car._color)#used outside of the class
bmw=Bmw()
```
Output:

```
Black
Inside the BMW Class Black
```
Private Variable: You cannot use Private variable outside a class but use it within a class . Don't forget to use "__" before the variable

```
class Car:
    __yearOfManufacture = 2017

    def Private_key(self):
        print("Private attribute yearOfManufacture: ",car.__yearOfManufacture)  # private variable only works with its own class


car=Car()
car.Private_key()
```
Output:

```
Private attribute yearOfManufacture:  2017
```
