<h2> List </h2>
A list is a collection of Python data values organized in a sequential order, with each value identified by an index. List is mutable and a list can contain elements of different datatypes.

There are several ways to create a new list. The simplest is to enclose the elements in square brackets[]
```
w = []                                           #empty list
x = [200,400,600,1000]                           #list with integer values
y = ["rock", "paper", "sizer"]                   #string values
z = ["magic", 9.0, 8, [1,3,5]]                   #multiple type values
```
A list can contain multiple datatypes even including a list in a single list.


As list is mutable, we can access the items of list; we can add and remove value into an existing list.
<h4> Index Operator </h4>

```
lst = ['red','white','lavender','black']
print(lst[2])
[print(lst[-3])]
```
Output:
```
lavender
white
```
```
s_2 = ['Startup','love020',"It's okay not to be okay"]
com = s_2[0] + " " + "was released on 2020."
print(com)
```
Output:
```
Startup was released on 2020.
```
Just like string, the numbering of list indexing always starts from zero.

To change value of a specific position of a list,we can re-assign new value of that index of a list.

For example,
```
s_li = ['apollo','space shuttle','vostok','soyuz','voskhod']
s_li[3] = 'gemini'
print(s_li)
```
Output:
```
['apollo', 'space shuttle', 'vostok', 'gemini', 'voskhod']
```
<h4>Append function</h4>

we can add items at the end of an existing list by using built-in append function.

```
my_li = ["magic", 9.0, 8, [1,3,5]]  
my_li.append('gilmore girls')
print(my_li)
```
Output:
```
['magic', 9.0, 8, [1, 3, 5], 'gilmore girls']
```

We can also add multiple list together, this is called list concetenation.
```
li_1 = ['Friends','Atypical','Witcher']
li_2 = ['Meteor garden','love020',"It's okay not to be okay"]
f_li = li_1 + li_2
print(f_li)
```
Output:
```
['Friends', 'Atypical', 'Witcher', 'Meteor garden', 'love020', "It's okay not to be okay"]
```
***REMEMBER,*** We can concetanate list with an other list; not other data type.
```
sports = ['cricket', 'football', 'volleyball']
y = sports + 5
print(y)
```
Output:
```
TypeError: can only concatenate list (not "int") to list
```
<h4>Length of a list</h4>

To know the number of items in a list, we can use len()
```
space_craft = ['apollo','space shuttle','vostok','soyuz','voskhod']
print(len(space_craft))
```
Output:
```
5
```
<h4>Looping through a list </h4>

```
llyst = ['ping pong', 9.0, 'Pringles', 8, 'rain', [1, 3, 5], 'vostok']
for i in llyst:
    print(i)
```
Output:
```
ping pong
9.0
Pringles
8
rain
[1, 3, 5]
vostok
```
***One thing to notice,*** We use square brackets for creating lists and also for indexing.
Indexing requires referencing an already created list while simply creating a list does not.
```
lst = [0]
n_lst = lst[0]

print(lst)                          #type --> list
print(n_lst)                        #type --> int
```
Output:
```
[0]
0
```
a list called lst being assigned to a list with one element, zero. Then, we see how n_lst is assigned the value associated with the first element of lst.

<h4>List Slicing</h4>

We can access a range of values in a list by using colon notation; this is called slicing. ***Remember,*** the ending value is exclusive in resulting list and slicing doesn't modify the content of original list.
```
STRUCTURE: list_name[start(inclusive):end(exclusive):step(default 1)]
```
```
lst_0 = ["Dairy milk", "Pringles", "Kitkat", "Coka-cola", "Harsheys", "Lays", "Cadbury"]
print(lst_0[1:6:2])                                   
print(lst_0)
```
Output:
```
['Pringles', 'Coka-cola', 'Lays']
['Dairy milk', 'Pringles', 'Kitkat', 'Coka-cola', 'Harsheys', 'Lays', 'Cadbury']     #slicing didn't modify original list
```
```
lst_1 = ["Dairy milk", "Pringles", "Kitkat", "Coka-cola", "Harsheys", "Lays", "Cadbury"]
print(lst_1[:])
```
Output:
```
['Dairy milk', 'Pringles', 'Kitkat', 'Coka-cola', 'Harsheys', 'Lays', 'Cadbury']
```
```
lst_2 = ['Dairy milk', 'Pringles', 'Kitkat', 'Coka-cola', 'Harsheys', 'Lays', 'Cadbury']
print(lst_2[-1:-3:-1])
```
Output:
```
['Cadbury', 'Lays']
```
```
lst_3 = ['Dairy milk', 'Pringles', 'Kitkat', 'Coka-cola', 'Harsheys', 'Lays', 'Cadbury']
print(lst_3[2:])
```
Output:
```
['Kitkat', 'Coka-cola', 'Harsheys', 'Lays', 'Cadbury']
```
```
lst_4 = ['Dairy milk', 'Pringles', 'Kitkat', 'Coka-cola', 'Harsheys', 'Lays', 'Cadbury']
print(lst_4[:4])
```
Output:
```
['Dairy milk', 'Pringles', 'Kitkat', 'Coka-cola']
```
```
lst_f = ['Dairy milk', 'Pringles', 'Kitkat', 'Coka-cola', 'Harsheys', 'Lays', 'Cadbury']
print(lst_f[::2])
```
Output:
```
['Dairy milk', 'Kitkat', 'Harsheys', 'Cadbury']
```
<h4>Access a list inside another list</h4>

```
tlst = ['white', 2, ['Pringles', 'Kitkat', 'Coka-cola'], 'lavender']
print(tlst[2][1])
```
Output:
```
Kitkat
```
<h4>Count method</h4>

this method is useful for counting the occurances of a particular item in a list.
```
lst = ["magic", 21, "snowball", [1,3,5], 3, "rain", [2, 4], "snowball", "lili" ]
y =lst.count("snowball")
print(y)
```
Output:
```
2
```
<h4>sort method</h4>

```
mlst_0 = ['bubble', 'dopamine', 'array', 'coronel', 'zem', 'lahore']
mlst_0.sort()
print(mlst_0)                                #notice this sorting format
```
Output:
```
['array', 'bubble', 'coronel', 'dopamine', 'lahore', 'zem']
```
<h4>reverse method</h4>

```
rlst = ['cricket', 'football', 'volleyball', 'baseball', 'softball', 'track and field', 'curling', 'ping pong']
rlst.reverse()
print(rlst)
```
Output:
```
['ping pong', 'curling', 'track and field', 'softball', 'baseball', 'volleyball', 'football', 'cricket']
```
<h4>insert method </h4>

when we use append method, the new value adds in the last position of a list; but using insert method, we can specify index of the new value.
```
mlst_1 = ['bubble', 'dopamine', 'array', 'coronel', 'zem', 'lahore']
mlst_1.insert(2, 'pegion')
print(mlst_1)
```
insert expects two arguments.
Output:
```
['bubble', 'dopamine', 'pegion', 'array', 'coronel', 'zem', 'lahore']
```
<h3> Removing elements from a list</h3>
<h4>pop(index) method</h4>

```
ths_0 = ['orange','space shuttle', 'track and field', 'curling', 'Coka-cola', 'Harsheys', 'vostok']
ths_0.pop(2)
print(ths_0)
```
Output:
```
['orange', 'space shuttle', 'curling', 'Coka-cola', 'Harsheys', 'vostok']
```
<h4>clear method</h4>

```
ths_1 = ['orange','space shuttle', 'track and field', 'curling', 'Coka-cola', 'Harsheys', 'vostok']
ths_1.clear()
print(ths_1)
```
Output:
```
[]
```
<h4>remove(one argument)</h4>

list.remove takes exactly one argument
```
ths_3 = ['orange', 'pineapple', 'strawberry', 'banana']
ths_3.remove('strawberry')
print(ths_3)
```
Output:
```
['orange', 'pineapple', 'banana']
```
<h4>index method</h4>

for knowing the index of any argument of a list, we have to assign it into a new variable.It returns only the first occurance.
```
klst = ['baseball', 'softball', 'track and field', 'array', 'coronel', 'curling', 'ping pong']
new = klst.index('track and field')
print(new)
```
Output:
```
2
```
<h4>To make a copy of items of the list into a new list, we can use [:] operator </h4>

```
my_lst = ['bubble','strawberry', 'dopamine', 'ping pong','coronel', 'zem']
new_lst = my_lst[:]
print(my_lst)
```
Output:
```
['bubble', 'strawberry', 'dopamine', 'ping pong', 'coronel', 'zem']
```
***Remember***, the copied list remains unchanged even if we change the original list.
```
m_lst = ['bubble','strawberry', 'dopamine', 'ping pong','coronel', 'zem']
nw_lst = m_lst[:]
m_lst.insert(2,'scream')
print(nw_lst)
```
Output:
```
['bubble', 'strawberry', 'dopamine', 'ping pong', 'coronel', 'zem']
```
