# OOP ( Object Oriented Programming) 

<img src="https://github.com/LWM-Community/Python/blob/main/Photos/oop.png"  alt="Our Post shared by Dev Community " width="400" height="400" align="right"/>


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
Example using all of the variables

```
#Public=membername
#Protected=_memberName
#Private=__memberName
class Car:
    numberOfWheels=4
    _color="Black"
    __yearOfManufacture=2017

    def Private_key(self):
        print("Private attribute yearOfManufacture: ", car.__yearOfManufacture) #private variable only works with its own class


class Bmw(Car):
    def __init__(self):
        print("Protected attribute color",self._color)#By using Inheritence we got Car class's variable

car=Car()
print("Public attribute numberOfWheels",car.numberOfWheels)
bmw=Bmw() # while we create this object . things under it's __init__ will be printed
car.Private_key()

```
Output:

```
Public attribute numberOfWheels 4
Protected attribute color Black
Private attribute yearOfManufacture:  2017
```
**Class variable & Instance Variable**

Instance Variable: Instance variable is variable dealing with the instance/object . You can change it's value outside of the class. You can access Instance variable by <Instance/Object name.variable name>

```
class Book():

    def __init__(self):
        self.x = 100  # instance variable

    def display(self):
        print(self.x)


b = Book()
print(b.x)  # printing instance variable

b.x=101 #changing the value of x
print(b.x)

```
Output:

```
100
101
```
Class Variable: Class Variable is valid for the class and can be called with its <class name. variable name>

```
class Book():
    x = 5  # class variable
    y=6

    def __init__(self):
        self.x = 100  # instance variable

    def display(self):
        print(self.x)


b = Book()
print("class variable",Book.x)  # printing class variable
print("instance variable",b.x)  # printing instance variable
print("class variable",Book.y)

#changng the class variable changes the value for class and instance
Book.y=7
print("class variable",Book.y)
print("instance variable",b.y)

```
Output:

```
class variable 5
instance variable 100
class variable 6
class variable 7
instance variable 7
```
**Instance method, Class method ,Static method**

Instance method: Instance method is method which can be used for instance/object . 

```
class MyClass():

    def __init__(self,x):
        self._x=x

    def method1(self):#instance method
        print(self._x)


value=MyClass(100)
value.method1()
```
Output:

```
100
```
Class method: class method can be used by the class and you have to create @classmethod to create a class method and it can be accessed through <Class name.method name()> . Again, you have to set cls as parameter of the class method

```
class MyClass():
    a=5
    
    #class method
    @classmethod
    def method2(cls): #cls refers to class object
        print(cls.a)

MyClass.method2()#calling class method (prints 5)
```
Output:

```
5
```
But,if you don't want to use "cls", you can use your desired parameter name

```
class MyClass():
    a=5


    #class method
    @classmethod
    def method2(class_method): #cls refers to class object
        print(class_method.a)


MyClass.method2()#calling class method (prints 5)
```
Output:

```
5
```
Static Method: Static method does not have any must parameter like self or cls . It just works like a random function we used to make 

```
class MyClass():

    @staticmethod
    def method3(m,n): #takes 2 value
        return m+n #returns their sum

object=MyClass()
print(object.method3(10,20))
```
Output:

```
30
```


**property method**
To get value from a method, you may set it as a property method using @property before the method name . You can access the property method using <object/instance name.method name> . Don't use () at the end of the method name . 

```
class Product:
    def __init__(self, x, y):
        self._x = x
        self._y = y

    @property  # to get any value using this method written  as   object.method or, p.value not like p.value()
    def value(self): #property method
        return self._x

    
p = Product(23, 24)
print(p.value) # you cannot use p.value()
```
Output:

```
23
```
Again you can set value of the property  method by using <@property method name.setter>

```
class Product:
    def __init__(self, x, y):
        self._x = x
        self._y = y



    @property  # to get any value using this method written  as   object.method or, p.value not like p.value()
    def value(self):
        return self._x

    @value.setter  # to set  value
    def value(self, val):
        self._x=val


p = Product(23, 24)
print(p.value)

p.value=100
print("After setting the new value, it is now",p.value)
```
Output:

```
23
After setting the new value, it is now 100

```
To delete a value from property method, you can use <@property method.deleter> 

```
class Product:
    def __init__(self, x, y):
        self._x = x
        self._y = y



    @property  # to get any value using this method written  a variable ex: object.method or, p.value not like p.value()
    def value(self):
        return self._x

    @value.setter  # to set a function to assign value
    def value(self, val):
        self._x = val

    # while we delete a value,this method will be applied ex: del p.value
    @value.deleter
    def value(self):
        print('Value  deleted')


p = Product(12, 24)
print("Property object has the 1st value",p.value)
#to delete the value use del and then objectname.variable name
del p.value
```
Output:

```
Property object has the 1st value 12
Value  deleted
```
**Dispatch method**
Dispatch method is used to work with specific thing . for example if you want to work with 3 integers or 3 float or float and an integer, you can create a custom method. 
Note: Don't forget to install multipledispatch package 

for example to work with 3 integers, you can use <@dispatch(int,int,int)> and then your desired method with 4 parameters including self .

```
@dispatch(int,int,int)#working for 3 integers
    def product(self,a,b,c):
```
Let's check a code 

```
from multipledispatch import dispatch
class my_calculator():

    @dispatch(int,int)#when we have 2 input, it will work
    def product(self,a,b):
        print("Product of 2 integers : ",a*b)

    @dispatch(int,int,int)#working for 3 integers
    def product(self,a,b,c):
        print("Product of 3 integers : ",a*b)
    @dispatch(float,float,float)#working for 3 floats
    def product(self,a,b,c):
        print("Product of 3 floats : ",a*b*c)
    @dispatch(float,int)#working for a int and a float
    def product(self,c,d):
        print("Product of 1 float and 1 integer : ",c*d)
c1=my_calculator()
c1.product(4,5)
c1.product(4,7,6)
c1.product(4.0,5.0,3.0)
c1.product(4.0,3)
```
Output:

```
Product of 2 integers :  20
Product of 3 integers :  28
Product of 3 floats :  60.0
Product of 1 float and 1 integer :  12.0
```
**Magic Method**
Magic method starts with __ and ends with __

Code:

```
class Fraction:
    def __init__(self,nr,dr=1):
        self.nr=nr
        self.dr=dr
        if self.dr<0:
            self.nr*=-1
            self.dr*=-1
        self.__reduce__()

    def show(self):
        print(f'{self.nr}/{self.dr}')



    def __str__(self):
         return f'{self.nr}/{self.dr}'

    def __repr__(self):
         return f'Fraction({self.nr}/{self.dr})'

    def __add__(self, other):#magic method __method__
        if isinstance(other,int):
            other=Fraction(other)
        f=Fraction(self.nr*other.dr+other.nr*self.dr)
        f.__reduce__()
        return f
    def __radd__(self, other):#reverse add
        return self.__add__(other)


    def __sub__(self, other):
        if isinstance(other,int):
            other=Fraction(other)
        f=Fraction(self.nr*other.dr-other.nr*self.dr)
        f.__reduce__()
        return f

    def __mult__(self,other):
        if isinstance(other,int):
            other=Fraction(other)
        f=Fraction(self.nr*other.nr,self.dr*other.dr)
        f.__reduce__()
        return f
    def __eq__(self,other):
        return (self.nr*other.dr)==(self.dr*other.nr)

    def __lt__(self, other):
          return (self.nr*other.dr)<(self.dr*other.nr)

    def __le__(self, other):
          return (self.nr*other.dr)<=(self.dr*other.nr)

    def __reduce__(self):
        h=Fraction.hcf(self.nr,self.dr)
        if h==0:
            return
        self.nr//=h
        self.dr//=h
    @staticmethod
    def something():   pass

```
**Protected method  , Private method**
You can use protected method outside of the class but cannot use private method outside of the method

```
class Product:
    def __init__(self):
        self.data1=10
        self._data2=20 #protected variable
    def methodA(self):
        pass
    def _methodB(self): #pprotected  method
        print("Hello to protected method")
    def __methodC(self):#private method
        print("Hola")


p=Product()
print(dir(p)) #You can see additionally _data2', '_methodB', 'data1', 'methodA'
print(p._data2) #accessing the protected variable
p._methodB() #calling the proteced method

```
Output:

```
['_Product__methodC', '__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__', '_data2', '_methodB', 'data1', 'methodA']
20
Hello to protected method
```
**Operator Overloading**
To set specific rules for a specific operator, we use operator overloading . For example, __add__ is used for "+" 
Check out this link: https://www.geeksforgeeks.org/operator-overloading-in-python/

If we want to add 2 different object one has 1 and 6 and other has 9 and 3, we will use operator overloading to do so

```
class Point:
    def __init__(self, x=0, y=0):
        self.x = x
        self.y = y

    def __str__(self): #if asked to print string type
        return "({0},{1})".format(self.x, self.y)

    def __add__(self, other): #works for + opetator
        x = self.x + self.y
        y = other.x + other.y
        return Point(x, y)


p1 = Point(1, 6)#worked for self
p2 = Point(9, 3)#other
print("P1 has 1st value",p1.x)
print("P1 has 2nd value", p1.y)
print("P2 has 1st value",p2.x)
print("P2 has 2nd value", p2.y)
print("Summation of p1+p2 is",p1+p2)#as p1 is first so self is for p1 and p2 gets others


```
To realize it in a better way,use Thonny IDE from this link (https://thonny.org/) and paste this code and debug . You can see how the code is proceeding
Ouput:

```
P1 has 1st value 1
P1 has 2nd value 6
P2 has 1st value 9
P2 has 2nd value 3
Summation of p1+p2 is (7,12)

Process finished with exit code 0

```
**Polymorphism**
There might be method of same name but to use them depending on their class, we use it like this

```
class Car:
    def start(self):
        print('Engine started')
    def move(self):
        print('Car is running')

    def stop(self):
        print('Brales applied')

class Clock:
    def move(self):
        print('Tick Tick Tick')

    def stop(self):
        print('Clock needles stopped')

class Person:
    def move(self):
        print('Person walking')
    def stop(self):
        print('Taking rest')
    def talk(self):
        print('Hello')


car=Car()
clock=Clock()
person=Person()

#this method will run with which instance you call it
def do_something(x):
    x.move()
    x.stop()


# calling with car instance
do_something(car) #car is an object of Car class

#calling with clock instance
do_something(clock) # clock is an object of Clock class

#calling with person instance
do_something(person) #person is an object of Person class
```
Output:

```
Car is running
Brales applied
Tick Tick Tick
Clock needles stopped
Person walking
Taking rest
```
**Inheritance**
Let's assume that your college has CSE , BBA department . They have few things in common. All of them have student ID card, they are from he same college . So,, while you want to take all the information of BBA student or CSE student , you can do one thing. You can create a class names Student which works for common purposes and you can create 2 different class which will work with other extra information like BBA Students with have marketing classes where CSE Students will have Labs. So, to work with this code , we can use inheritance . So, while creating BBA Student class , we will use the "Student" class in the peremeter to mean inheritance
Note: Here "Student": class will be called parent class and "BBA Student " class will be student class

Again , to use something from the parent class, you will have to use <super().parent class's method name>

```
class Student:
    def __init__(self, name='Just a student', dept='nothing'):
        self.__name = name
        self.__department = dept

    def set_department(self, dept):
        self.__department = dept

    def get_name(self):
        return self.__name

    def set_name(self, name):
        self.__name = name

    def __str__(self):
        return f"Name: {self.__name} \nDepartment: {self.__department}\n"



# write your code here
class BBA_Student(Student):
    def __init__(self, name="default", department="BBA"):
        super().__init__(name, department)#used Student class's __init__ method
        print("I am a BBA Students . We do marketing courses")

class CSE_Student(Student):
    def __init__(self,name="default",department="CSE"):
        super().__init__(name,department)#used Student class's __init__ method
        print("I am a CSE Student and I have a lots of lab to complete")

print(BBA_Student('Karim Ali'))#using BBA_Student class inherited Student class
print(CSE_Student('Mitul'))# using CSE_Student class inherited Student class
```
Output:

```
I am a BBA Students . We do marketing courses
Name: Karim Ali 
Department: BBA

I am a CSE Student and I have a lots of lab to complete
Name: Mitul 
Department: CSE

```


