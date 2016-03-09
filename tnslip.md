
# thenotsolongintroductiontopython

Hello folks, This article is a short introduction to python, or rather should say not so long one. This article is a casual read, and has been written for those people who have prior knowledge in some other programming language. This read, was designed by keeping in mind about giving a gentle introduction of python to programmers, and from nowhere, it is supposed to replace a tutorial.


Python was designed by [Guido Van Rossum](https://twitter.com/gvanrossum), who currently works at Dropbox, and is also known as BDFL, i.e. Benevolent Dictator For Life in the python community for his continues contributions in the process of Python development. Python is a multi-paradigm language, which was basically designed for ..... well idk, I can't see any specific area to point out, but can see almost everywhere.

Unless explicitly mentioned, all the code snippets are for python3. Lets start with the classic code sample, here is the hello world


```python
print("Hello, World!")
```

    Hello, World!


Python `print` function is powerful, it has capability to dump almost everything to stdout, unlike C, C++, or JAVA where you need to break the complex data structure down to the built-in ones in order to display them. Actually, the fact is, built in data structures in python are real world and programmer friendly, causing you less trouble, we shall elaborate on these built-in types in a moment. Besides this, `print` function also provides you a bunch of other options so that the output is good to visualize.


```python
print("Hello", "World", "from", "python", 3, sep = " ", end = "!!")
```

    Hello World from python 3!!

Did you look at that? Wasn't that impressive? A mixture of different datatypes can be printed by using a separator `sep` and an ending string `end`.

Just for the sake of information, the print statement in python2 has been [changed](https://www.python.org/dev/peps/pep-3105/) to the print function in python3. And one more thing, the last link points to a PEP, [Python Enhancement Proposals](https://www.python.org/dev/peps/), the name is self-explanatory, hope you land there after a few months of hard work!

Oh lord, wait a minute, Did I say python2 and/or python3? I'm sorry, actually, there are lot of controversies on (or rather problems with) this topic, which one to choose, 2 or 3? So instead of you reading a lot of things on Internet about which one to choose, I would suggest that unless you are bound by some constraints always go with python3. If you looking forward to learn python, then python3 should be the choice. If you are going to develop something from scratch, do it in python3. However, in case you are working on something that requires support from a module that has been written for python2 and not python3, you don't have a choice. Developers don't switch to python3 because they don't want to break their code, because either the code has been written for python2 or it is dependent on modules designed for python2. FYI, linux ships with both python2 as well as python3, however, python2 is the default, and is recommended not to change it for the same reason.

For more discussion, you can hear to [Kenneth Reitz](https://github.com/kennethreitz) on this [podcast](https://talkpython.fm/episodes/show/6/requests-pycon-and-python-s-future).

Okay! Where were we? We were discussing the power of `print` function. Here is another one


```python
print("{0} rises in the {1}.".format('Sun', 'east'))
print(".{:>15} ...this is a separator... {:_<15}.".format('Hello', 'World'))
```

    Sun rises in the east.
    .          Hello ...this is a separator... World__________.


The later is good for aligning stuff in form of columns.

In case, if you did not notice, the arguments to `format` function are in single quotes. This is because there is nothing like a character in python, instead strings are considered elementary types. `'a'` is similar to `"a"`, which is similar to `"""a"""` or `'''a'''`. But, you should use either single quotes or double quotes, just stick to the convention of when to use which. This helps when your string consists of double quotes or a single quotes, as you can use the other one to wrap it up, avoiding backslashes and increasing the readability. 

The triple quotes are used for docstrings. These are comments. Oops, sorry, not comments, actually more than comments. Single line comments are followed by `#` symbol. But [Docstrings](https://www.python.org/dev/peps/pep-0257/) are more than comments. They are special because you can access them with help of `__doc__` attribute associated with that object. Docstrings are written during writing a module(logically speaking here, it may be a class, package, method, function, or whatever), and they explain what the module does.


```python
import numbers

def square(x):
    """Checks if x is an integer and then returns its square, otherwise None."""
    if isinstance(x, numbers.Integral):
        return x*x
    return None

print(square.__doc__)
```

    Checks if x is an integer and then returns its square, otherwise None.


Docstrings can be single line (the one shown above) or multiline (as shown below).


```python
def square():
    """This is a multiline docstring. This can be big and can go across lines,
    just like this one. All the docstrings greater than 72 characters should go into a
    multiline docstring, and not in one line.
    """
    pass
```

We have seen a function here, we shall be back on it later. Lets keep exploring other built-in types.

We have Booleans from class 'bool' which can be either `True` or `False`. Similarly, there are numeric types `int`, `long`, `float`, and `complex`. `complex` is notable here.


```python
print(complex(5.2, -4))
print(complex(5))
print(complex(0))
```

    (5.2-4j)
    (5+0j)
    0j


Besides these, there are byte arrays. But we won't be focusing on them. Some others are more popular. Lets have a look at `list`. Lists are simply collection of elements. Lists are by far one of the most powerful data structures I have seen in any language.


```python
fancy_list = [0, 1, 2, "Sun", "moon", True]
fancy_list.append(3.1415)
print(fancy_list)
fancy_list[2] = False
print(fancy_list)
fancy_list.remove(0)
print(fancy_list)
```

    [0, 1, 2, 'Sun', 'moon', True, 3.1415]
    [0, 1, False, 'Sun', 'moon', True, 3.1415]
    [1, False, 'Sun', 'moon', True, 3.1415]


When said collection of elements, then its literally a collection. This collection has no restriction on types, unlike traditional languages which have arrays which consists of only similar type elements. You can append things to list, lists are mutable, so you can change any element by random access (index starts with 0). Besides these, lists also support slicing, i.e. you can select lists partially like `list_name[starting_index:ending_index:steps]`, here starting_index is inclusive while ending_index is exclusive.


```python
fancy_list = [0, 1, 2, "Sun", [100, 101] ,"moon", True, False, 3.1415, "sunday"]
days = ["saturday", "sunday"]
print(fancy_list[3])                          # random access
print(fancy_list[2:])                         # everything after 2nd index(inclusive)
print(fancy_list[:5])                         # everything uptil 5th index(exclusive)
print(fancy_list[0:8:2])                      # from 0th to 7th index, pick everything by steps of 2 (inclusive)
print(fancy_list[::-1])                       # reversed list
print(fancy_list[:3] + days)                  # you can combine(not exactly combine) arrays
```

    Sun
    [2, 'Sun', [100, 101], 'moon', True, False, 3.1415, 'sunday']
    [0, 1, 2, 'Sun', [100, 101]]
    [0, 2, [100, 101], True]
    ['sunday', 3.1415, False, True, 'moon', [100, 101], 'Sun', 2, 1, 0]
    [0, 1, 2, 'saturday', 'sunday']


But lists have to badly pay for all these features and flexibility. They consume a lot of memory space in order to provide efficient functionality of so many features. If you wish to reduce the memory consumption (and to a certain extent the time complexity), then you have some other options too. You can use the [array](https://docs.python.org/3/library/array.html) module if you wish to interface with C. In other cases, you can choose the [array](https://docs.scipy.org/doc/numpy-1.10.0/reference/generated/numpy.array.html) from the numpy module, which itself is pretty efficient. Going a step further, we have [numexpr](https://github.com/pydata/numexpr) which does better cache utilization and uses multi-threading capabilities to accelerate the evaluation of long arrays!

[Tuples](https://docs.python.org/3.5/library/stdtypes.html#tuple) are another built-in types that are completely identical to lists, except that they are immutable, i.e. the values of its elements can't be changed. The benefit of immutable objects is that you can have a fixed memory allocated to them and you need not to worry about modification of its contents. This also makes tuples [faster](http://stackoverflow.com/a/3340881) than lists.

You use parenthesis instead of square brackets in tuples.


```python
fancy_tuple = (5, 8, 13, 21, "34")
print(fancy_tuple[1:4])                         #slicing the tuple
print(fancy_tuple.index(13))                    #get index of an element
print(dir(fancy_tuple))                         #print all attributes associated to the object passed to dir()
```

    (8, 13, 21)
    2
    ['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__iter__', '__le__', '__len__', '__lt__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'count', 'index']


The last statement displays all the attributes that are associated to the object which has been passed to `dir` function.

The interesting thing that python provides here is tuple unpacking, i.e. you can expect multiple things from RHS to get assigned to multiple things on LHS. Lets see this in action.


```python
fancy_tuple = (5, 8, 13, 21, "34")
first, *middle, last = fancy_tuple              # paritioning tuple into first, middle, and last
print(first, " | ", middle, " | ", last)
first, *_, last = fancy_tuple                   # use underscore for a throwaway variable
print(first, " | ", middle, " | ", last)
nested_list = [[1,2,3], 4, 5, 6, 7]
(a, b, c), *_, d = nested_list                  # nested structures can also be unpacked!
print(a, b, c, d)
```

    5  |  [8, 13, 21]  |  34
    5  |  [8, 13, 21]  |  34
    1 2 3 7


Just make sure that you don't create ambiguity, unpacking is deterministic, that's why python doesn't expect you to have 2 or more starred expressions. These tricks can be used in case of swapping the elements, it looks simple, clear, and concise.


```python
a = 5
b = 7
print(a, b)
a, b = b, a
print(a, b)
```

    5 7
    7 5


This is how python enhances readability. The same can be used to generate a fibonacci series.


```python
first = 0
second = 1
print(first)
for num in range(10):
    print(second)
    first, second = second, first + second  
```

    0
    1
    1
    2
    3
    5
    8
    13
    21
    34
    55


Now before discussing dictionaries, let me clear some pending explanations from the above code snippets. Firstly, we use indentation in python to mark nesting of statements, for instance, look at the `for` loop above. The block is indented using [4](https://www.python.org/dev/peps/pep-0008/#indentation) spaces. The best practice is to use spaces for indenting, although I always hit the tab key, but I make sure that my editor does the conversion to spaces for me. The bad habit would be to use tab. And the worst one would be to use mixture of both tabs and spaces!

If you may have noticed, we have a `range` called in the `for` construct. It returns a list, the code below should help you understand this.


```python
print(list(range(10)))
print(list(range(5, 15)))
print(list(range(5, 15, 2)))
print(list(range(15, 5, -1)))
print("I know I have cheated there, but I shall cover it up when I discuss generators!")    # ignore this
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    [5, 6, 7, 8, 9, 10, 11, 12, 13, 14]
    [5, 7, 9, 11, 13]
    [15, 14, 13, 12, 11, 10, 9, 8, 7, 6]
    I know I have cheated there, but I shall cover it up when I discuss generators!


`range()` function represents data like an [Arithmetic Progression](https://en.wikipedia.org/wiki/Arithmetic_progression). It has a form like `range(starting_number, ending_number, common_difference)`.

The other widely used type is dictionary, it is a mapping of a key to a value. You can access the value by specifying the key as index, in almost constant time. Python dictionary is internally implemented as hash table which is stored in contiguous block of memory. Collisions are generally resolved by linear probing, CPython does this pseudorandomly. Lets not focus on [internal implementation](https://youtu.be/C4Kc8xzcA68) and turn our attention to the usage.


```python
world = {"India": "Asia", "Russia": ["Asia", "Europe"], "Spain": "Europe", "Argentina": "SA", "USA": "NA", "Brazil":"SA", "France": "Europe", "South Africa": "Africa"}
north = {"Russia": ["Asia", "Europe"], "China": "Asia", "Canada": "NA", "USA": "NA", "Sweden": "Europe"}
print(world["India"])                                     # Retrieve value using a key
print(world.get("Australia", "country not found!"))       # get() method allows you to specify default value if key is not found in dictionary
print(north.keys())                                       # display all keys
print(north.values())                                     # display all values
print(north.items())                                      # display key-value pairs
print(world.keys() & north.keys())                        # find common keys in 2 dictionaries
print(world.keys() - north.keys())                        # find keys in world that are not in north
```

    Asia
    country not found!
    dict_keys(['Canada', 'Russia', 'Sweden', 'China', 'USA'])
    dict_values(['NA', ['Asia', 'Europe'], 'Europe', 'Asia', 'NA'])
    dict_items([('Canada', 'NA'), ('Russia', ['Asia', 'Europe']), ('Sweden', 'Europe'), ('China', 'Asia'), ('USA', 'NA')])
    {'USA', 'Russia'}
    {'Argentina', 'India', 'France', 'Spain', 'Brazil', 'South Africa'}


These sort of operations can be used to filter the contents of the dictionary. For eg, if we want all countries except  `"India"` and `"USA"`, then we do


```python
world = {"India": "Asia", "Russia": ["Asia", "Europe"], "Spain": "Europe", "Argentina": "SA", "USA": "NA", "Brazil":"SA", "France": "Europe", "South Africa": "Africa"}
print({key:world[key] for key in world.keys() - {"India", "USA"}})
```

    {'South Africa': 'Africa', 'Spain': 'Europe', 'Argentina': 'SA', 'Brazil': 'SA', 'Russia': ['Asia', 'Europe'], 'France': 'Europe'}


Did you notice the value associated with `"Russia"`? It is a list! This means you can map any object to a key in a dictionary. Can you guess where does this become handy, mixture of lists and dictionaries? Yes, json! Managing json data fetched from various web APIs becomes very simple.

This was what I meant when I said data is stored in programmer friendly(or rather easy to use) format.

Like tuple unpacking, there is [dictionary unpacking](https://www.python.org/dev/peps/pep-0448/) too(from python3.5)! There also exist [sets](https://docs.python.org/3.5/library/stdtypes.html#set) which work as usual. They are also internally implemented as hash tables, and hence, give O(1) lookup time at average. You can find union, intersection, and symmetric difference of 2 sets. Set also has attributes to check whether another set is its subset or a superset.

Okay, Lets look at some other things from the clutter that we should have picked up by now. Python comes with a Read Evaluate Print Loop(REPL), which allows programmer to test short code snippets. So, open the terminal, type `python3`, and start playing around with whatever comes next.

Comparison operators are as usual. Additionally `==` operator checks for equivalence of values. There also exists `is` operator that checks for identity equivalence. Everything in python is an object. Each object has its identity which is returned by [id()](https://docs.python.org/2/library/functions.html#id) function as long integer, passing that object as its argument. Identity of an object in python is analogous to a memory location in C. So it is possible for 2 identifiers to have same identity, but not always!


```python
s = "the quick brown fox jumps over the lazy dog"
a = "the"
b = s.split(' ')[0]
print(id(a))
print(id(b))
print(a == b)
print(a is b)
```

    139987176560712
    139987176667992
    True
    False


So always use `==` when comparing values and `is` when comparing identities. We have another operator, known as the membership operator `in`. This example is self-explanatory.


```python
print(5 in [1, 2, 3, 5, "wow"])
print("Star" in {"Star": ["Sun"], "Planets": ["Earth", "Mars", "Jupiter"]})
print(5 in range(5))
print(5 in {1,2,3,4,5})
```

    True
    True
    False
    True


There also exists a built-in constant, instance of a `NoneType` class, `None`, which is used to "represent the absence of a value, as when default arguments are not passed to a function", as the documentation states. It is equivalent to `NULL` or `nil` or whatever similar you have encountered till yet.

Available boolean operators are `not`, `and`, `or` in the descending order of priority, with the later 2 being short-circuit operators.

We have a straightforward `if` construct, `if-elif-else`, where `elif`(stands for "else if") and `else`, both are optional. For the truth value testing,


```python
# The prefered way is
val1 = True
val2 = False
if val1:
    pass
elif not val2:
    pass
else:
    pass

# This is not the prefered way
if val == True:
    pass
```

The same convention goes with the while loop. We have a for statement too, which is generally used to iterate over a sequence.


```python
planets = ["Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn"]
for i in planets:
    print(i)
for i in range(5):
    print(i)
```

    Mercury
    Venus
    Earth
    Mars
    Jupiter
    Saturn
    0
    1
    2
    3
    4


However, this does not provide you with the index number when using for contruct. So, there exists a better way to do so.


```python
# The preferable way
planets = ["Mercury", "Venus", "Earth", "Mars", "Jupiter", "Saturn"]
for index, value in enumerate(planets):
    print(index, value)
# Avoid doing this
for i in range(6):
    print(planets[i])
```

    0 Mercury
    1 Venus
    2 Earth
    3 Mars
    4 Jupiter
    5 Saturn
    Mercury
    Venus
    Earth
    Mars
    Jupiter
    Saturn


You can also use `for` to generate initial lists. This way is generally prefered in python. Whenever I say generally prefered in python, that means it is the pythonic way of doing things. There is always a particular way of solving problems in each language, not exactly a way, but a preferable choice of writing the code if there exist more than one way of achieving something. And probably, this is the point where I lack, so if you find something wrong, please notify me or push a commit to [myrepo](github.com). So here is how you can make lists so that you can use it further in your code.


```python
squares = [i*i for i in range(20)]                          # squares of non-negative numbers upto 19
squaresgt10 = [i*i for i in range(20) if i > 10]            # squares of numbers [11, 20)
matrix = [[True for col in range(4)] for row in range(5)]   # 5by4 2-D matrix with all values True
print(squares)
print(squaresgt10)
print(matrix)
```

    [0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100, 121, 144, 169, 196, 225, 256, 289, 324, 361]
    [121, 144, 169, 196, 225, 256, 289, 324, 361]
    [[True, True, True, True], [True, True, True, True], [True, True, True, True], [True, True, True, True], [True, True, True, True]]


## abouttheauthor

I am Piyush Deshmukh, I am an undergrad student from India. What drives me to write this article is my passion towards learning and my love for python(3). I have been programming since my high school. Please visit my [profile](https://piyushdeshmukh.github.io) if you want to be in touch.
