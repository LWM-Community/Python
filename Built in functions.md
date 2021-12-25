

**abs()**	Returns the absolute value of the given number and returns a magnitude of a complex number.

**all()**	Checks whether all the elements in an iterable are truthy values or not. It returns True if all elements in the given iterable are nonzero or true. Else, it returns False.

**any()**	Returns True if at least one element in the given iterable is truthy value or boolean True. Returns False for empty or falsy value (such as 0, False, none).

**ascii()**	Returns a string containing a printable representation of an object for non-alphabats or invisible characters such as tab, carriage return, form feed etc.

**bin()**	Converts an integer number to a binary string prefixed with '0b'.

**bool()**	Converts a value to the bool class object containing either True or False

**bytearray()**	Returns a bytearray object which is an array of the given bytes. The bytearray class is a mutable sequence of integers in the range of 0 to 256.

**bytes()**	Returns an immutable object of the bytes class initialized with the sequence of integers in the range of 0 to 256

**callable()**	Returns True if the object passed is callable, False if not. In Python, classes, methods, and instances are callable because calling a class returns a new instance, instances are callable if their class includes `__call__()` method.

**chr()**	Returns the string representing a character whose Unicode code point is the integer

**classmethod()**	Transforms a method into a class method

**complex()**	Returns a complex number (an object of complex class) for the provided real value and imaginary*1j value, or converts a string or number to a complex number.

**dict()**	Creates a dictionary object from the specified keys and values, or iterables of keys and values or mapping objects.

**delattr()**	Deletes the named attribute from the object if the object allows it.

**dir()**	Returns a list of valid attributes of the specified object. If no argument passed, it returns the list of names in the current local scope.


**divmod()**	Returns a tuple of two numbers where first number is the quotient and the second is the remainder.

**exec()**	Executes the Python code block passed as a string or a code object. The string is parsed as Python statements and then executed.

**enumerate()**	Returns an object of enumerate class for the given iterable, sequence, iterator, or object that supports iteration. The returned enumerate object contains tuples for each items of the iterable that includes an index (from start which defaults to 0) and the values obtained from iterating over iterable.

**filter()**	Calls the specified function which returns boolen for each item of the specified iterable.

**float()**	Returns an object of the `float` class that represent a floating point number converted from a number or string.

**format()**	Allows multiple substitutions and value formatting. This method lets us concatenate elements within a string through positional formatting.

**frozenset()**	Returns an immutable set object with elements from the given iterable. Iterables can be list, set, dictionary, tuple, string.

**getattr()**	Returns the value of the attribute of an object. If the named attribute does not exist, default is returned if provided, otherwise AttributeError is raised.

**hex()**	Converts an integer number to a lowercase hexadecimal string prefixed with "0x".

**hash()**	Returns the hash value of the specified object. The hash values are used in data storage and to access data in a small time per retrieval, and storage space only fractionally greater than the total space required for the data or records themselves. In Python, has values are used to compare dictionary keys to access values.

**hasattr()**	Checks if an object of the class has the specified attribute.

**help()**	It displays the documentation of modules, functions, classes, keywords etc.

__import__()	The __import__() method is called by the import statement. This method can change the semantics of the import statement which is strongly discouraged .

**id()**	Returns an identity of an object. In Python, every variable or literal values are objects and each object has a unique identity as an integer number that remains constant for that object through out its life time.

**int()**	Returns an integer object constructed from a number or string, or return 0 if no arguments are given.

**input()**	Allows user to input values.

**isinstance()**	Checks if the object is an instance of the specified class or any of its subclass.

**issubclass()**	Checks if the specified class is the subclass of the specified subclass.

**iter()**	Returns an iterator object that represents a stream of data for the iterable object or sentinel.

**len()**	Returns the length of the object. Returns total elements in an iterable or number of chars in a string.

**list()**	Returns a list from an iterable passed as arguement.

**map()**	Applies the specified function to every item of the passed iterable, yields the results, and returns an iterator.

**max()**	Returns the largest value from the specified iterable or multiple arguments.

**memoryview()**	Returns a memory view object of the given object. The memoryview object allows Python code to access the internal data of an object that supports the buffer protocol without copying.

**min()**	Returns the lowest value from the specified iterable or provided multiple arguments.

**next()**	Returns the next item from the iterator by calling its __next__() method.

**object()**	Returns a new featureless object. The object class is the base class of all classes in Python.

**oct()**	Converts an integer to octal string prefixed with "0o".

**open()**	Opens the file (if possible) and returns the corresponding file object.

**ord()**	Returns an integer representing the Unicode character.

**pow()**	Returns the specified exponent power of a number.

**print()**	prints the given object to the console or to the text stream file.

**property()**	Returns the property attribute.

**range()**	Returns an object of the range class which is an immutable sequence type. The `range()` method returns the imutable sequence numbers between the specified start and the stop parameter.

**repr()**	Returns a string containing a printable representation of an object. The repr() function calls the underlaying __repr__() function of the object.

**reversed()**	Returns the reversed iterator of the given sequence. It is same as but in reverse order. Internally, it calls the `__reversed__()` method of the sequence class. If the given object is not a sequence, then override __reversed__() method in the class to be used with the reversed() function

**round()**	Returns a floating-point number rounded to the specified number of decimal point.

**set()**	Returns an object of the set class from the specified iterable and its elements. A set object is an unordered collection of distinct hashable objects. It cannot contain duplicate values. Visit [set]('/python/set') for more information.

**setattr()**	Sets the specified value to the specified attribute of the specified object. This is the counterpart of getattr() method.

**slice()**	Returns a portion of an iterable as an object of the slice class based on the specified range. It can be used with string, list, tuple, set, bytes, or range objects or custom class object that implements sequence methods __getitem__() and __len__() methods.

**sorted()**	Returns a sorted list from the items in an iterable.

**str()**	Returns an object of the str class with the specified value.

**sum()**	Returns the total of integer elements starting from left to right of the given iterable.

**super()**	Returns a proxy object that allows us to access methods of the base class.

**tuple()**	Creates an empty tuple or converts the specified iterable to a tuple.

**type()**	Either returns the type of the specified object or returns a new type object of the specified dynamic class, based on the specified class name, base classes and class body.

**vars()**	Returns the __dict__ attribute of the specified object. A __dict__ object used to store an object's writable attributes.

**zip()**	Takes iterables, aggregates them in a tuple, and return it.


Check more from this link: https://www.tutorialsteacher.com/python/builtin-methods
