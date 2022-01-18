<h2> Tuple </h2>

A tuple is a sequence of items of ***any type*** and is immutable. So, once we assign values to any variable we can not change them.

The representation of a tuple is a comma-separated sequence of values, enclosed in parentheses(). 
```
n_tup = ('rebert', 2009, [10, 'mango', 2.9], 'rebellion', 'ring')
print(type(n_tup))
```
Output:
```
<class 'tuple'>
```
If we want to declare single value inside a tuple, python might consider it as a normal variable inside parenthesis.
```
val =('julia')
print(type(val))
```
Output:
```
<class 'str'>
```
 How can we sort this?

we have to use a comma before closing the parenthesis. Like this:
```
val = ('julia',)
print(type(val))
```
Output:
```
<class 'tuple'>
```
<h4>Tuple constructor </h4>
We can also declare a tuple using tuple constructor.
For this, we have to declare a tuple using DOUBLE first parenthesis.

``` tuple(('items',)) ```
```
dble_tpl = tuple(('cherry', 'pingpong', 'hockey', 'basket', 'yellow', 'brown'))
print(dble_tpl)
print(type(dble_tpl))
```
Output:
```
('cherry', 'pingpong', 'hockey', 'basket', 'yellow', 'brown')
<class 'tuple'>
```
<h4>Immutability of Tuple: </h4>

```
n_tup = ('rebert', 2009, [10, 'mango', 2.9], 'rebellion', 'ring')
n_tup[1] = 2010
print(n_tup)
```
Output:
```
TypeError: 'tuple' object does not support item assignment
```
As tuple is immutable, we are not allowed to change/remove any items after assigning them once in a variable.

BUT,
 <h4> Changing the value of tuple </h4>

Although tuples are immutable(unchangable), we can still change the items of a tuple by ***converting the tuple into a list.*** Change the value in the list, and then, convert the list back to the tuple.
```
ftup = ('bunny', 'herion', 'fan', 'van')
convert_list = list(ftup) 
convert_list[1] = 'fire'
new_tuple = tuple(convert_list)
print(new_tuple)
```
Output:
```
('bunny', 'fire', 'fan', 'van')
```
<h4> Delete a tuple </h4>

We can ***DELETE*** the whole tuple completely:
```
stup = ('yellow', 'paper', 'daisy')
del stup 
print(stup)
```
Output:
```
NameError: name 'stup' is not defined.
```
In python, immutable objects has a fixed id which is the identity of an object, a location​ in ​memory​.

Items with same values have the same id.
```
e_tup = (25,26,27,25,40)
print(id(e_tup[0]))
print(id(e_tup[3]))
print(id(e_tup[1]))
```
Output:
```
4372317168
4372317168
4372317200
```
<h5>In above output, these values are not constant .Everytime we run the code, items with same value will have same value but the values will be changed everytime we run the code. </h5>

```
e_tup = (25,26,27,25,40)
if id(e_tup[0]) == id(e_tup[2]):
    print("true")
else:
    print("Value assigned in the 4th position will be True. ")
```
Output:
```
Value assigned in the 4th position will be True.
```
<h4>tuple indexing</h4>

```
atup = ('major lazer', 'selena', 'ariana', 2013, 'swift', 'sarika')
print(atup[1])
print(atup(-1))
```
Output:
```
selena
sakira
```
<h4>  Tuple Slicing </h4>

```
char = ('Triyon', 'Jon', 'Jaime', 'Sansa', 'Arya', 'Theon', 'Snow')
print(char[1:6:2])
```
Output:
```
('Jon', 'Sansa', 'Theon')
```
```
char1 = ('Triyon', 'Jon', 'Jaime', 'Sansa', 'Arya', 'Theon', 'Snow')
print(char1[-5:-2])
```
Output:
```
('Jaime', 'Sansa', 'Arya')
```
<h4> Tuple concetenation </h4>

```
tup =('cherry', 'pingpong', 'hockey') + ('Sansa', 'Arya', 'Theon', 'Snow')
print(tup)
```
Output:
```
('cherry', 'pingpong', 'hockey', 'Sansa', 'Arya', 'Theon', 'Snow')
```
<h4> Looping through a tuple </h4>

```
l_tup = ("Julia", "Duplicity", 2009, "Actress", "Atlanta",1920,  "Georgia")
for i in l_tup:
    print(i)
```
Output:
```
Julia
Duplicity
2009
Actress
Atlanta
1920
Georgia
```
<h4> Length of a tuple </h4>

```
t_ttup = ('Jon', 300, 'Duplicity', 200, 'Jaime', 1520, 'Sansa')
print(len(t_ttup))
```
Output:
```
7
```
<h4> Tuple Unpacking </h4>

when we create a tuple, we assign values to it. this is called "packing" a tuple:

Packing a tuple:
``` stars = ('Sirius', 'Canopus', 'Vega', 'Rigel', 'Procyon') ```

We can also extract the values back into variables. this is called tuple "unpacking".

Unpacking a tuple:
```
stars = ('Sirius', 'Canopus', 'Vega', 'Rigel', 'Procyon')
(c, d, a, f, e) = stars
print(d)
print('a:', c, 'b:', d, 'c:', a, 'd:', f, 'e:', e)
```
Output:
```
Canopus
a: Sirius b: Canopus c: Vega d: Rigel e: Procyon
```
REMEMBER, The number of variables must match the number of values in the tuple, if not, you must use an asterisk(*) to collect the remaining values as a list.
```
tup_1 = ("rain", "fall", "sun", "snow", "wind", "cry")
(one, *two, last) = tup_1
print(two)
```
Output:
```
['fall', 'sun', 'snow', 'wind']
``` 

<h4> Enumerate() </h4>

An enumerator function adds a counter of iterable numbers(sequential numbers) to the provided data structure of integers, characters or strings and many more .The data structure might be any list, tuple, dictionary or sets. If the counter is not provided by the user, then it starts from 0 by default. Based on the number provided the enumerator function iterates.

Syntax: ``` enumerate(iterable, start) ```

Note: The iterable must be an object that supports iteration.

```
nup = ['rain', 'rain', 'go', 'away']
enum = enumerate(nup)
now_tup = tuple(enum)
print(now_tup)
```
Output:
```
((0, 'rain'), (1, 'rain'), (2, 'go'), (3, 'away'))
```
```
nup = ['rain', 'rain', 'go', 'away']
enum = enumerate(nup, 3)
now_tup = tuple(enum)
print(now_tup)
```
Output:
```
((3, 'rain'), (4, 'rain'), (5, 'go'), (6, 'away'))
```
<h4>Looping over an iterable object </h4>

```
x = ['No', 'matter', 'what', 'you', 'say', ',', 'no', 'matter', 'what', 'you', 'do!']
for i in enumerate(x):
    print(i)
```
Output:
```
(0, 'No')
(1, 'matter')
(2, 'what')
(3, 'you')
(4, 'say')
(5, ',')
(6, 'no')
(7, 'matter')
(8, 'what')
(9, 'you')
(10, 'do!')
```

<h4> count </h4>

```
p = ('rain', 'rain', 'go', 'away')
y = p.count('rain')
print(y)
```
Output:
```
2
```

<h4> index </h4>

returns the first occurance of the given value of the tuple

```
n = (2, 4, 5, 45, 78, 12, 2, 3)
here = n.index(2)
print(here)
```
Output:
```
0
```
