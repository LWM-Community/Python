# Python Basics 

**Python print**

```
print("Hello there from Mitul!")#printing a string

print(1,2,3,4)#printing 4 values

var=100
print('The value is',var)#printing the variable

print(1,2,3,4,sep='+')#separate the values based on the sep

print(1,2,3,4,sep='*',end='&')#separate the value based on sep and add end  at the last

print('I like to eat {0} and {1}'.format('bread','butter')) # use the value from format as index meaning {0} for the 1st value and {1} for the 2nd value

print('I like to eat {1} and {0}'.format('bread','butter'))



```

**Python File**

```
import os
print(os.getcwd()) #shows current directory

#changing working directory to Filetest
os.chdir('E:\My-University-Life-Learning\Semester 1\Filetest')
#checking what are there in the directory
print(os.listdir())
#checking the current directory
print(os.getcwd())

#to make a directory
os.mkdir('New Directory')

#used to rename a directory
os.rename('New Directory','Updated Directory')


#remove a file
os.remove('<file_name>')

#remove a directory
os.rmdir('Updated directory')

```


**Python Numbers**

```
"""
0b or 0B : Binary number prefix
0o or 0O : Octal Number prefix
0x or 0X : Hexadecimal number prefix
"""

#checking if 100 is int or float or complex
value=100
print(type(value))
print(isinstance(value,int))
print(isinstance(value,float))
print(isinstance(value,complex))

#checking if 100.24 is int or float or complex
value1=100.24
print(type(value1))
print(isinstance(value1,int))
print(isinstance(value1,float))
print(isinstance(value1,complex))



#checking if 100+5j is int or float or complex
value2=100+5j
print(type(value2))
print(isinstance(value2,int))
print(isinstance(value2,float))
print(isinstance(value2,complex))



print(0b1101)# Ob means binary
print(0xab) #0x means hexadecimal
print(0o23) #0o means octal

#using Decimal module to calculate float point summation , multiplication etc
#1
data=0.1+0.2
print(data)
#solving this issue:
from decimal import Decimal as D
print(D('0.1')+D('0.2'))

#2
data_1=1.20*2.50
print(data_1)
print(D('1.2')*D('2.50'))


#using fraction
from fractions import Fraction as F
print(F(1.5))
print(F(5))
print(F(1,5))


#using math module
import math
print(math.pi)
print(math.cos(10))
print(math.log(10))
print(math.log10(10))
print(math.exp(10))
print(math.factorial(5))
print(math.sinh(10))


#python random module

import random

print('Random number ->',random.randrange(5,15)) #printing any random number between 5 to 15

#choosing something from the list
day_list=['Sat','Sun','Mon','Wed','Thu','Fri']
print(random.choice(day_list))

#shuffling a list
print(day_list)
print(random.shuffle(day_list))
print(day_list)

#any element randomly
print(random.random())
```

**Python Turtle Module**

```
import turtle
scrn = turtle.Screen()                  #creates a graphics window
sponge = turtle.Turtle()                #creates a turtle whose name is sponge
sponge.forward(200)                     #object.method(parameter)
sponge.left(90)
sponge.forward(100)

#sponge is an instance of Turtle class
#scrn is an instance of Screen class

```

**Python namespace**

```

#same value like a=2 and b=2 has the same address
a=2
print('id(2)=',id(2))
print('id(a)=',id(a))


a=3
print('id(3)=',id(3))
print('id(a)=',id(a))

b=2
print('id(2)=',id(2))
print('id(b)=',id(b))

```
Output:
id(2)= 2342642018640
id(a)= 2342642018640
id(3)= 2342642018672
id(a)= 2342642018672
id(2)= 2342642018640
id(b)= 2342642018640

**Python Scoping**


```
def outer_function():
    global a
    a=20
    def inner_function():
        global a
        a=30
        print('Third a=',a)
    inner_function()
    print('Fourth a=',a)

a=10
print('First a=',a)
outer_function()
print('Second a=',a)
```


**Python  nonlocal variable**

Nonlocal:

```
def outer():
    x="local"
    def inner():
        nonlocal x #making the x variable of outer() global
        x="hola"
        print("inner",x)

    inner()
    print("outer:",x)

outer()
```

**Python Iterator**

iter() method

```
list_1=[44,77,11,33]
iter_1=iter(list_1) #creating iterator object by calling iterclass
print(iter_1)
```

next() method:

```
list_1=[44,77,11,33]
iter_1=iter(list_1)
print(next(iter_1)) #now using next class while using iter_1 object to get 1st value
print(next(iter_1)) # to get 2nd value as used 2nd time

print(iter_1.__next__()) #get 3rd value

```


Making an iterator using class:

```
#making an iterator
class Pow_of_two:
    def __init__(self,max=0):
        self.max=max
    def __iter__(self):
        self.n=0
        #print("self.n value:",self.n)
        return self
    def __next__(self):
        if self.n<=self.max:
            #print("self.n",self.n)
            #print("self.max",self.max)
            result=2**self.n # 2^(self.n)
            self.n+=1
            return result
        else:
            raise StopIteration

#print(Pow_of_two.__doc__)
a=Pow_of_two(4) #a is an object of Pow_of_two
i=iter(a) #using the object a in iter method
print(next(i))
print(next(i))
print(next(i))


"""process :
a object
i object of next method 
print(next(i)) which is print(next(4))
self.n=0
self.max=4
result =2^0
return 2^0
again,
self.n=1
self.max=4
result =2^1
return 2^1

self.n=2
self.max=4
result =2^2
return 2^2"""

```
Using for loop to iterate:

```
#1
list_1=[3,2,5,6,8]
for i in list_1:
    print(i)
#2
for i in range(7,11):
    print(i)
```


**Python Inheritance**

```
class myBird:
    def __init__(self):
        print("myBird class constructor is executing...")
    def whatType(self):
        print("I am a bird...")
    def canSwim(self):
        print("I can swim.....")

class myPenguin(myBird):
    def __init__(self):
        super().__init__() #what is it's work!
        print("myPenguin class constructor is executing...")
    def whoisThis(self):
        print("I am Penguin....")
    def canRun(self):
        print("I can run faster......")


pg1=myPenguin()
pg1.whatType()
pg1.whoisThis()
pg1.canSwim()
pg1.canRun()
```

Multiple Inheritance

```
#Multiple Inheritance
class Base1:
    pass
class Base2:
    pass
class MultiDerived(Base1,Base2):
    pass

class Base1:
    def funcBase1(self):
        print("funcBase1 is executing...")
class Base2:
    def funcBase2(self):
        print("funcBase2 is executing....")
class Base3:
    def funcBase3(self):
        print("funcBase3 is executing...")

class MultiDerived(Base1,Base2,Base3):
     def funcMultiDerived(self):
         print("funcMultiDerived() is executing ....")

md1=MultiDerived()
md1.funcBase1()
md1.funcBase2()
md1.funcBase3()
md1.funcMultiDerived()




```
Overriding (inheritance)
```
class Student:
    def __init__(self, name='Just a student', dept='nothing'):
        self.name = name
        self.dept = dept
    def set_department(self, dept):
        self.dept = dept
    def get_name(self):
        return self.name
    def set_name(self,name):
        self.name = name
    def __str__(self):
        return 'Name: '+self.name+' Department: '+self.dept
#write your code here


class BBA_Student(Student):
    def __init__(self, name='default', dept='BBA'):
        self.name = name
        self.dept = dept
        
    




print(BBA_Student())
print(BBA_Student('Humpty Dumpty'))
print(BBA_Student('Little Bo Peep'))
```




Private Inheritance 
(You cannot override private properties of a parent class)
```
class Student:
    def __init__(self, name='Just a student', dept='nothing'):
        self.__name = name
        self.__department = dept
    def set_department(self, dept):
        self.__department = dept
    def get_name(self):
        return self.__name
    def set_name(self,name):
        self.__name = name
    def __str__(self):
        return 'Name: '+self.__name+' Department: '+self.__department
#write your code here


class BBA_Student(Student):
    def __init__(self, name='default', dept='BBA'):
        super().__init__(name=name, dept=dept)
    




print(BBA_Student())
print(BBA_Student('Humpty Dumpty'))
print(BBA_Student('Little Bo Peep'))
```


**Python Exception**

AssertionError , AttributeError, EOFError, FloatingPointError, GeneratorExit , ImportError, IndexError

```
try:
    '''Block for trying the code'''
    a="hi"
    b=int(a)
except:
   print("Exception Caught")
```
Along with finally

example 1:
```
try:
    '''Block for trying the code'''
    a="hi"
    b=int(a)
except:
   print("Exception Caught")
   
finally:
   print("Finally block") 
```

example 2:

```
try:
    a=int(input("Please enter the first number: "))
    b=int(input("Please enter the second number: "))
    if (a<0): # for negative numbers
        raise TypeError
    c=a/b
    print("{} / {} = {}".format(a,b,c))
except ZeroDivisionError:
    print("Division by zero is not positive")
except ValueError: # if not given digits or number
    print("The data types are not proper")
except TypeError: # for negative numbers case
    print("The data is not in  range")
except NameError: # if used new variable
    print("The data  items are not defined")


```
User defined exception

```
#creating an exception class
class VoterEligibility(Exception):
    def __init__(self):
        super() # The super() function in Python makes class inheritance more manageable and extensible.

try:
   age="12"
   if age<18:
       raise VoterEligibility
except TypeError:
    print("Age is not numeric")
except VoterEligibility:
   print("Age is less than 18")
else:
   print("Age is greater than or equal 18")
finally:
   print("End of the program")



```

**Nested Dictionary**


```
people={1:{'name':'Karim','age':'27','sex':'Male'},2:{'name':'Rahima','age':'21','sex':'Female'}}

for p_id,p_info in people.items():
    print("\nPerson ID:",p_id)

    for i in p_info:
        print(i+':',p_info[i])
```
Output:

```
Person ID: 1
name: Karim
age: 27
sex: Male

Person ID: 2
name: Rahima
age: 21
sex: Female

```

**Python Operator overloading**

```
class myPoint:
    def __init__(self,x=0,y=0): #constructor
        self.x=x
        self.y=y

    def __str__(self):  #if there is any string value passed, we then use this
        return "{0},{1}".format(self.x,self.y)

    def __add__(self, other):
        x=self.x+other.x
        y=self.y+other.y
        return myPoint(x,y)

    def __lt__(self, other):
        self_mag=(self.x**2)+(self.y**2)
        other_mag=(other.x**2)+(other.y**2)
        return self_mag < other_mag  #if self_mag < other_mag then will return True


p1=myPoint(1,2)
p2=myPoint(4,5)
print(p1)
print(p2)
print(p1<p2)
print(p1+p2)
print(p1.__lt__(p2))
print(p2.__lt__(p1))
```

**Python Generator**

Example 1:
```
#creating a generator function
def my_generator():
    n=1
    print("This is printed first")
    yield n #yielt pauses the function all its state and later continues from there
    #important to use next()

    n+=1
    print("This is printed second")
    yield n
    n+=1
    print("This is printed at last")
    yield n


a=my_generator()
#Iterrating using text
next(a)
next(a)
next(a)
print("Using for loop..")
#Iterating using for loop
for item in my_generator():
    print(item)
```
Example 2:

```
#reverse a string
def reverse_string(my_string):
    length=len(my_string)
    for i in range(length-1,-1,-1):
        yield my_string[i]


for char in reverse_string("WORLD"):
    print(char)
```

**Python Decorator**

Example 1:
```
#Demonstration
def make_decorated(func):
    def inner_function():
        print("I got decorated")
        func()
    return inner_function()
def simple_func():
    print("I am a simple function")

decor=make_decorated(simple_func)
decor()  #calling decor
```
or,

```
#Demonstration
def make_decorated(func):
    def inner_function():
        print("I got decorated")
        func()
    return inner_function()
@make_decorated #make decorated will be used
def simple_func():
    print("I am a simple function")

simple_func()  #calling the simple_func()
```
Example 2:

```
def my_smart_div(func):
    def inner_func(x,y):
        print("I am dividing ",x," and ",y)
        if y==0:
            print("Oops! Division by Zero is illegal")
            return
        return func(x,y)
    return inner_func # YOU CANNOT use inner_func()

#Generally , we decorate a function and reassign it as , go_divide=my_smart_div(go_divide)
@my_smart_div #when the decoration function is called, it will take go_divide() as  func and work
def go_divide(a,b):
    return a/b

print(go_divide(20,2))
print(go_divide(20,0))

```
**Python Matrix**

```
#a is  a 2D matrix
a=[['Roy',80,90,100,110,120],
   ['John',10,20,30,40,50],
   ['Dave',20,30,40,60,70]]
#b is a nested list
b=[['Mitul',80,90,100,110,120],
   ['Johny',10,20,30,40],
   ['David',20,30,40,60,70]]

print(a)
print(b)
```

**Python Regular Expression**

Searching using search

Example 1:
```
import re

if re.search("ape","The ape was at the apex"):
    print("There is an ape")
```

Example 2:
finditer()
 

```
import re
str_0="The ape was at the apex"
for i in re.finditer("ape.",str_0):
    tup_0=i.span() #span returns a tuple
    print(tup_0)

    print(str_0[tup_0[0]:tup_0[1]])#as tup_0 has 2 values (4,8) so, we get from str_0[4] to str_0[8] . Thus ape and later for (19,23) we get apex
"""As we get ape first so , we get 4 index and new word starts from 8th index
the span() returns (4,8) and again we get apex and this we got again (19,23)"""
```
re.findall()

```
import re
str_0="Cat rat mat fat pat"
update_animal=re.findall("[crmfp]at",str_0)#c/r/m/f/p at
for i in update_animal:
    print(i)
```

or,

```
import re
str_0="Cat rat mat fat pat"
update_animal=re.findall("[c-mC-M]at",str_0)#from c to m and from C to M
for i in update_animal:
    print(i)
```
or, 

```
import re
str_0="Cat rat mat fat pat"
update_animal=re.findall("[^Cr]at",str_0)#other than C and r
for i in update_animal:
    print(i)
```

or,

```
import re

str_0="rat cat mat pat"
regex=re.compile("[cr]at")
print(regex)
str_0=regex.sub("owl",str_0)#starting with [cr] will be replaced with owl
print(str_0)
```

Raw string

```
import re
string_0="Here is \\stuff"

#we won't get \\stuff here
#print("Find \\stuff : ",re.search("\\stuff",string_0))

#we can now get \\stuff index
#print("Find \\stuff : ",re.search("\\\\stuff",string_0))


#using raw string as r
print("Find \\stuff : ",re.search(r"\\stuff",string_0))
```

or,

```
import re
str_0="F.B.I. I.R.S. CIA"
print("Matches :",len(re.findall(".\..\..",str_0)))
print("Matches :",re.findall(".\..\..",str_0))
```

Convering newlines to one line
```

import re
str_0="""This is a long 
string that goes 
on for many lines"""
print(str_0)

#removing newlines
regex=re.compile("\n")

str_0=regex.sub(" ",str_0)
print(str_0)

#other than this we can use \b,\f,\r,\t,\v

```
Checking number

```
import re
str_0="12345"
#will check if there is any single number
print("Matches : ",len(re.findall("\d",str_0)))
print("Matches : ",re.findall("\d",str_0))
```
or,

```
import re
#matche value between 5 numbers only
if re.search("\d{5}","12345"):
    print("It is a zip code")

str_0="123 12345 123456 1234567"
#matches value that are between 5 and 7 digits
print("Matches :",len(re.findall("\d{5,7}",str_0)))
```
or,

```
import re

#\w is the same as [1-zA-Z0-9]
#\W is the same as [^a-zA-Z0-9]
str_0="412-555-1212"
if re.search("\w{3}-\w{3}-\w{4}",str_0):
    print("It is a phone number")

if re.search("\w{2,20}","Ultraman"):
   print("It is a valid name")
```
or,

```
import re
#\s or \s means [\f\n\r\t\v]
if re.search("\w{2,20}\s\w{2,20}","Toshio Muramatsu"):
    print("It is a valid full name")
```
or,

```
import re
#+ matches 1 or more character
print("Matches : ",len(re.findall("a+","a as ape bug")))
print("Matches : ",re.findall("a+","a as ape bug")) # these 3 words have a once at a time
```
Email scrapping

```
import re

#1to 20 lowercase and uppercase letters, numbers,plus ._%+ (means we can have any letters and _ and % and +)
#An @ symbol
#2 to 20 lowercase and uppercase letters, numbers, plus .- (means that we can have any letter and a - too)
#A period
#2 to 3 lowercase and uppercase letters
emaillist="db@aol.com m@.com @apple.com db@.com +a@max.com  %jola@hmail.com  karim_saheb@gmail.com  karim-raza@gmail.com  hola@gmai-l.com"
print("Email Matches : ",len(re.findall("[\w._%+-]{1,20}@[\w.-]{2,20}.[A-Za-z]{2,20}",emaillist)))
print("Email Matches : ",re.findall("[\w._%+-]{1,20}@[\w.-]{2,20}.[A-Za-z]{2,20}",emaillist))
```

**Python list comprehension**

Using a for loop

```
list_0=[]
for i in 'python':
    list_0.append(i)
print(list_0)

```

List comprehension

```
list_0=[i for i in "human"]
print(list_0)

```

Lambda function

```
list_0=list(map(lambda i:i,"human")) # creating a map object and then making it a list 
                                    #lambda as i variable and is picking eaching value from the string "human"
print(list_0)
```
Nested if with list comprehension

```
list_0=[y for y in range(100) if y%2==0 if y%5==0] # y will be in the list in range from 0 to 99 and that has to be divisible by 2 and 5
print(list_0)
```
 or 

```
obj=["Even" if i%2==0 else "Odd" for i in range(10)] # for i in range 0 to 99, if i%2==0 then even or else
```

Transpose matrix

```
matrix=[[1,2],[3,4],[5,6],[7,8]]

"""
Matrix:
[1 2]
[3 4]
[5 6]
[7 8]"""

"""Transpose
[1 3 5 7 ]
[2 4 6 8 ]
"""

transpose=[[row[i] for row in matrix]for i in range(2)]
"""i has range(0,1) 
fow gets a value first [1,2] 
then [1,2][0]=1
[[1][]]
then [1,2][1]=2
thus 
[[1][2]]
and like this we have [[1,3,5,7],[2,4,6,8]] 
which is 
[1 3 5 7 ]
[2 4 6 8 ]"""
print(transpose)
```

**Recursion**

```
def fact(n):
    if n<=1:
        return 1
    return n*fact(n-1)
print("Factorial of 5 is",fact(5))
```
**Deep copy and shallow copy**
Normal copy

```
list_0=[[1,2,3],[4,5,6],[7,8,9]]
list_1=list_0
print(list_0)
print(list_1)
list_1.append([10,11,12])
#both id's are same
print(id(list_0))
print(id(list_1))
print(list_0)
print(list_1)
```
Output:
Both id's are same 
```
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
2440548853184
2440548853184
[[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12]]
[[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12]]
```

Shallow Copy
id's are different and if one is changed , other is not updated
```
import copy

old_list=[[1,2,3],[4,5,6],[7,8,9]]
new_list=copy.copy(old_list)
#both id's are different now
print(id(old_list))
print(id(new_list))
print(old_list)
print(new_list)

#now if we update old list, no change is made to the new list
old_list.append(['new update'])
print(old_list)
print(new_list)
```
Output:

```
1710618912384
1710618781312
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
[[1, 2, 3], [4, 5, 6], [7, 8, 9], ['new update']]
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```
Deep copy
id's remain different but if one is changed then other is changed too

```
import copy
old_0_list=[[1,1,1],[2,2,2],[3,3,3]]
new_1_list=copy.deepcopy(old_0_list)
#id's are different
print(id(old_0_list))
print(id(new_1_list))
#here if one is updated, other is updated too
print(old_0_list)
print(new_1_list)

old_0_list[1][0]=0
print(old_0_list)
print(new_1_list)
```
Output:

```
1571582711616
1571582580544
[[1, 1, 1], [2, 2, 2], [3, 3, 3]]
[[1, 1, 1], [2, 2, 2], [3, 3, 3]]
[[1, 1, 1], [0, 2, 2], [3, 3, 3]]
[[1, 1, 1], [2, 2, 2], [3, 3, 3]]
```

Lambda
anonymous function is taken as lambda

```
a=lambda x: x*2 #means anonymous function has variable called x and x=x*2
#we can call this anonymous function with the name a as it is assigned there
print(a(10))
```
or,

```
list_0=[1,2,3,4,5]
#filter will take all values of list_0 and will return x for which  (x%2==0)
new_list=list(filter(lambda x:(x%2==0),list_0))
print(new_list)
```
or,

```
list_0=[1,2,3,4,5]
#filter will take all values of list_0 and will return x for which  (x%2==0)
new_list=list(map(lambda x:x*2,list_0))
print(new_list)

#Output
#[2, 4, 6, 8, 10]

```

**Python Assert**

```
def avg(marks):
    assert len(marks)!=0 #when we want to state that what should be done ex: here we dont want that len(marks) remain 0
    #if the statement in assert is true, then there is no error but if the statement is false, it stops and shows an error
    return sum(marks)/len(marks)


marks=[] #the method won't work for this function
print(avg(marks))

#Output:
#AssertionError

```
or,

```
def avg(marks):
    assert len(marks)!=0,"List is empty" #when we want to state that what should be done ex: here we dont want that len(marks) remain 0
    #if the statement in assert is true, then there is no error but if the statement is false, it stops and shows an error
    return sum(marks)/len(marks)


marks=[] #the method won't work for this function
print(avg(marks))


#Output:
#AssertionError: List is empty
```

**Python Property**
property() is a built in function mcreates and returns a property object
property(fget=None,fset=None,fdel=None,doc=None)
property object has getter method , setter method and delete method

```
class Temp_Celcius:
    def __init__(self,temperature=0):
        print("Assigning temperature value")
        self.__temperature=temperature

    def convert_to_fahrenhite(self):
        return (self.__temperature*1.8)+32

    def get_temperature(self):
        print("Getting temperature value")
        return self.__temperature
    def set_temperature(self,value):
        if value<-273:
            raise ValueError("Temperature below -273 is not possible ")
        print("Setting temperature value")
        self.__temperature=value


    temperature=property() #temperature=property(get_temperature,set_temperature)
    #assigning getter method fget
    temperature=temperature.getter(get_temperature) #method name assigned
    #assigning fset
    temperature=temperature.setter(set_temperature)
c=Temp_Celcius(5)#setting the value of c
print(c.temperature)#getting the value of c


c.temperature=100
print(c.temperature)

#Output:
#Assigning temperature value
#Getting temperature value
#5
#Setting temperature value
#Getting temperature value
#100

```
**Python Closure**

```
def print_message(message):#a closure function
    def print_message_inner():
        print(message) # print_message_inner can access this message variable
    return print_message_inner
val=print_message("Assalamualaikum!") # print_message has been passed with a value "Assalamualaikum"
#and val has the reference then of print_message_inner . so it can be said as the print_message_inner
val() #calling print_message_inner 

#Output:
#Assalamualaikum!
```

or,

```
def multiplier_outer(val):
    def multiplier_inner(inp):
        return val*inp
    return multiplier_inner

times_03=multiplier_outer(3) #here multiplier_outer has been assigned 3
#times_03 has the reference of multiplier_inner
#thus calling it with a parameter returns 3*9 =27
print(times_03(9))

#Output:
#27
```
## Thanks to all the contributors ❤️
<a href = "https://github.com/LWM-Community/Python/graphs/contributors">
  <img src = "https://contrib.rocks/image?repo=LWM-Community/Python"/>
</a>


