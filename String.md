<h2> String </h2>

***String is a sequence of ordered characters (alphabets-lower case, upper case, numeric values, special symbols).*** 

Strings are either enclosed with single qutation marks('),double quotation marks(''). Also we can write multi line string using triple qutations(''', " " " both) The character order is always from left to right.
```
print("Hello! I am mouly")
print('Helloo! I am Mouly')
print('''This is
a multi line 
string and we
call it "Doc-Strings" ''')
```
Output:
```
Hello! I am mouly
Helloo! I am Mouly
This is
a multi line 
string and we
call it "Doc-Strings" 
```
we can use either single quotation or double quotation as long as we are consistant about which qutation we are using
```
print("He was in the dead sea while listening 'Ocean Eyes'")
```
Output:
```
He was in the dead sea while listening 'Ocean Eyes'
```
This qutation sequence can easily be maintained by using preceding backslash which is called as an ***escape character( \ )***
```
print('I manage because I have to. Because I\'ve no other way out')
print("Don't you know,\"How can you ignore?\"")
```
Output:
```
I manage because I have to. Because I've no other way out
Don't you know,"How can you ignore?"
```
An ***empty string*** also holds an indexing position
```
print(" ")                                     #empty string
print(' ')
```
Output:
```


```
<h4>Type</h4>

this built-in fuction returns the type of an object
```
name = "alan walker"  
print(type(name))                             #type of name variable
```
Output:
```
<class 'str'>
```
Also,
```
p = "5"                                      #this is a string
q = 5                                        #this is an integer
print(type(p))
print(type(q))
```
Output:
```
<class 'str'>
<class 'int'>
```
Even though p and q might look same to you.. their types are different and there are different consequences for this. 
```
p = "5"
q = 5
print(p)
print(q + 45)
```
Output:
```
5
50
```
but 
```
p = "5"
q = 5
print(p + 45)                                 #this will give an error
print(q)
```
Output:
```
TypeError: can only concatenate str (not "int") to str
```
Here, p is a string. Even though 5 happens to look like a number, in python it's just a sequence of characters and we can't add a number to a sequence of characters.
we can add them if we cast this p string into an integer.
```
p = "5"
q = 5
print(int(p) + 45))                          #this won't give an error
print(q)
```
Output:
```
50
5
```
```
p = "5"
print(p + "45")                              #string concetenation
```
Output:
```
545
```
When we call a int of float to cast a string it needs to be a valid number.
```
p = "20 taka"
print(p + 25)
```
Output:
```
TypeError: can only concatenate str (not "int") to str
```
So, python can't convert this string into integer.

Strings are sequential collection datatype.This means a string is actually a collection of single characters.

<h4>Indexing</h4>

We can access an individual character of a string or part of a string using the indexing operator.
For accessing individual character by it's position or ***index value***. This index value always begins at ***zero***

Indexing can be done in two ways:

***Positive Indexing*** is used to access characters from the left side of a string and it always starts from 0 and ends at the last character of the string. 

***Negative Indexing*** is used to access characters from the right side of a string and it starts from -1 and ends at the first character of the string.
<img src=https://github.com/Mouly22/Read-and-Learn-Python/blob/main/string%20indexing.png  alt="String indexing " width="1000" height="400" align="center"/>

***REMEMBER,*** A string with six characters have entities from 0 through 5. So if we want to access a 5th character of a string we'll use an index of 4.

The basic string indexing structure 
```
string_name[index_value]
```
```
xmple = "we want to access"
print(xmple[0])
print(xmple[2])   
print(xmple[8])                                  #positive indexing
print(xmple[-1])                                 #negative indexing
print(xmple[18])                                 #index out of range
print(xmple[1.5])                                #type error
```
Output:
```
w

t
s
IndexError
TypeError
```

the built-in function ***len()*** helps us determine the length of a string. So the last index of a stirng will always be ***one less*** than the length of that string.
```
len(string)
```
```
xmple = "we want to access"
print(len(xmple))                               #length of a string
```
Output:
```
17
```
If we want to access last character of a string we can do either of them from below:
```
xmple = "we want to access"
print(xmple[len(xmple)-1])
print(xmple[-1])
```
Output:
```
e
e
```
<h4>Slicing</h4>

Slicing is used for getting a substring of a particular string.This allows us to create a sub-string that is more than one character long. Colon(:) is used as a slicing operator.

***Keep in mind*** that, the slice operator leaves the original operator intact.

Basic structure of slicing
```
string_name[beginning : end : step_size]
```
beginning: The index where slicing starts (inclusive). If not provided, by default starts from index 0.

end: The index where slicing stops(Not inclusive). If not provided, by default includes the rest of the string after “beginning”.

step : increment of the index value. If not provided, by default the value is 1.

```
xmple = "we want to access"
print(xmple[1:9:1])
```
Output:
```
e want t
```
In this example,the colon used in this slicing operator will return the characters from index 1 upto index 8(so not including index 9) and the increment will be 1.
<h4>String Operators</h4>
<h5> Concatenation </h5>
We can ***concatenate*** strings by using the plus(+) sign.
```
var1 = "we want"
var2 = "to visit a"
var3 = "zoo"
var =  var1 +" "+ var2 +" "+ var3             #concetenation of a string
print(var)
```
Output:
```
we want to visit a zoo
```
Notice one thing, this + sign doesn't add any ***space*** while concatenating. 
<h5>Repetition </h5>

We can create a new string with the specified number of copies of the input string using this method.
```
v = "repeat4time"*4
print(v)
```
Output:
```
repeat4timerepeat4timerepeat4timerepeat4time
```
<h4>Built-in methods</h4>

***It's important to remember that, Python is IMMUTABLE.*** Immutable means once it has been created its value cannot be changed.
So, each time we have to modify the values, we need to make a copy of the original one and make changes to the duplicate one.
```
me = "Abira"
me[1] = "e"
```
Output:
```
TypeError: 'str' object does not support item assignment
```
Python has some built-in method to access or process characters in string.

For example,

<h4>count(substring) method</h4>
we can use the count method to count the occurances of a particular substring.
```
place = "I want to visit USA"
print(place.count("i"))
```
Output:
```
2
```
As python is ***case-sensitive,*** we can't access I here cause the ASCII value of I is different than i***

<h4>index(substring) method</h4>

we can use the index method to find the index of the ***first occurance*** of a given substring.
```
place = "I want to visit USA"
print(place.index("i"))
```
Output:
```
11
```
<h4>Upper() and lower() method</h4>

Upper returns the ***copy** of a given string in all uppercase letters; while lower returns the copy of a given string in all lowercase letters.
```
place = "I want to visit USA"
print(place.upper())
print(place.lower())
```
Output:
```
I WANT TO VISIT USA
i want to visit usa
```
upper or lower method takes no arguments.

<h4>strip() method</h4>

this strip method returns the copy of a string by removing the ***whitespaces*** from before and after letters.

Whitespaces refers to any character that represents a space in text like a tab,a space or a new line character.

```
new = "   Well this is another line   !     "       #Strips all whitespace characters from both ends.
print(new.strip())
```
Output:
```
Well this is another line   !
```
Notice, the whitespace between characters are not removed, only the before and after letters whitespaces are removed.

<h4>replace(oldstring, newstring) method</h4>

the replace method replace every instance of oldstring with newstring in a string.
```
exm = "wd ard hdrd"
nexm = exm.replace('d','e')
print(nexm)
```
Output:
```
we are here
```
<h4> split method</h4>

Split helps us breaking sentences of a string into more managable pieces.

Split takes a ***delimiter*** and splits the string into sub-strings.The method returns a list where each item is a sub-string that is cut at every instance of that delimeter.

For example,

```
song = "Tell me why? Aint noting but a heartache. Tell me why? Aint noting but a mistake"
print(song.split("?"))
```
Output:
```
['Tell me why', ' Aint noting but a heartache. Tell me why', ' Aint noting but a mistake']
```
This output comes as a list
Here "?" is the delimeter.. so It will cut in those places and won't return the delimeter in output.

```
x = "Library is a place where you can find peace"
print(x.split(" "))
```
Output:
```
['Library', 'is', 'a', 'place', 'where', 'you', 'can', 'find', 'peace']
```
Here my delimeter is a space. So the resulting list will include every word in that sentence but no spaces.
```
x = "Library is a place where you can find peace"
print(x.split("a"))
```
Output:
```
['Libr', 'ry is ', ' pl', 'ce where you c', 'n find pe', 'ce']
```
So, the split method won't include the delimeter in the list it returns.

<h4>join method</h4>

The inverse of the split method is join. We can choose a desired separator string, (often called the glue) and join the list with the glue between each of the elements.

```
x = ["*light blue?", "sky", "it's raining hard","colin, where you go","?*"]
y = "! "
p = y.join(x)
print(p)
```
Output:
```
*light blue?! sky! it's raining hard! colin, where you go! ?*
```
We can also use empty string or multi-character strings as glue.
