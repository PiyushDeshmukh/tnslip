
# thenotsolongintroductiontopython

So, is it the case that you have got some time free on your schedule? And you have heard a lot of about python. How python is changing the world? Why programmers fall in love with it? What makes it so special?

Interested in knowing this, or rather feeling it? Attracted towards the language? Interested in getting acquainted with it? Wish to see some of the python scripts in action? So you are at the correct place, this article has been written to be read casually. Bear in mind, this document was designed by keeping in mind about giving a gentle introduction of python and from nowhere, it is supposed to replace a tutorial.


Python was designed by [Guido Van Rossum](https://twitter.com/gvanrossum), who currently works at Dropbox, and is also known as BDFL, i.e. Benevolent Dictator For Life in the python community for his continues contributions in the process of Python development. Python is a multi-paradigm language, which was basically designed for .........  well idk, I can't see any specific area to point out, but can see almost everywhere.

Python focuses a lot on readability. As it is said, "A code is written once, but read many times.", python focuses on both, the writability and the readability. With respect to writability, I mean that the speed of development of a project in python is generally higher than that of any other language. Program performance matters, but programmer performances also matters equally. Quoting [Donald Knuth](https://en.wikipedia.org/wiki/Donald_Knuth), "Premature optimization is the root of all evil". As python is a high level language, i.e. you need not to go into low level implementation of something, this saves you a lot of time. Implementing something is quick, and saves a lot of time, the time that you could have lost during maintainance because you were unnecessarily optimizing something that wasn't of enough worth. You can start and easily reach a working model. On the same side, readability is also one of the main purpose of writing code in python, maintainance is painless, and far more less frustating than other languages. Ofc, this has to do a lot with your code writing habits, but it always counts for each language, so makes no difference here. Writing bad code in python is possible, but that is not what is preferable, if you stick to conventions, you will be happy, atleast happier than the programmers of other langauges.

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

The triple quotes are used for docstrings. These are comments. Oops, sorry, not comments, actually more than comments. (Single line comments are followed by `#` symbol.) But [Docstrings](https://www.python.org/dev/peps/pep-0257/) are more than comments. They are special because you can access them with help of `__doc__` attribute associated with that object. Docstrings are written during writing a module(logically speaking here, it may be a class, package, method, function, or whatever), and they explain what the module does.


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

[Tuples](https://docs.python.org/3.5/library/stdtypes.html#tuple) are another built-in types that are completely identical to lists, except that they are immutable, i.e. the values of its elements can't be changed. The benefit of immutable objects is that you can have a fixed memory allocated to them and you need not to worry about modification of its contents further during the execution. This also makes tuples [faster](http://stackoverflow.com/a/3340881) than lists.

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

Now the fun part, the keys to a dictionary can be anything which is immutable, for eg strings in the above code. But since tuples are also immutable, so we can give them a chance too!

Consider the following dictionary of points, that tells the quadrant in which the point lies.


```python
quadrant = {}
quadrant[1, 2] = 'I'
quadrant[1, 1] = 'I'
quadrant[-1, 1] = 'IV'
quadrant[-1, -2] = 'III'
quadrant[1, -1] = 'II'
print(quadrant)
```

The tuple provided as the key, need not to limit its size to 2, it can be as big as possible. So a key of tuple of size 3 would look like `octant[5, 6, -7] = 'V'`. I think that's enough on dictionaries, probably wee should move forward now.

Everything in python is an object, I mean, everything in python is internally implemented as an object. As a consequence, they have attributes associated with them, you can have a list of those using `dir()`.

Python is strongly typed language and it does not do implicit type conversions. It is expected from the programmer to do all the type castings explicitly so that it is always clear what sort of data object has been binded to a variable. For instance, when you do `int("42")`, you know the obtained value is an integer, and if `float("3.1415)`, then the obtained value is float. 

This is one of the key principles on which the language was built. As [The Zen of Python](https://www.python.org/dev/peps/pep-0020/) states, "Explicit is better than implicit." This not only deals with explicit type casting, but a programming habit to do anything explicitly, like passing errors or declaring namespaces, a word on both of these later.

PEP20 deals with preferred way of doing things with python. PEP20 has 20, sorry 19, such good habits expected to be encorporated by the programmers. The 1, in my opinion, has probably been left by keeping in mind that such a list can never be completed as there is no perfect way of doing one thing. So they wanted to give a space to that futuristic way that does something in a more better way, the more pythonic way! I will try to illustrate each of them(19) or atleast tell you about before we encounter EOF.

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


So always use `==` when comparing values and `is` when comparing identities. Actually in python, we don't have variables storing some values in them, instead we have names which are nothing but just a binding to some data value which is stored in the memory. So names and their bindings to some data are like many to one mapping i.e. we can have multiple names bound to the same data, as in the case when `a = 5` and then `b = a`. If in the code later, we change `b` to 7, then the object bound to `a` also changes its value(in fact it is the same object).

We have another operator, known as the membership operator `in`. This example is self-explanatory.


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


You can also use `for` to generate initial lists. This way is generally prefered in python. Whenever I say generally prefered in python, that means it is the pythonic way of doing things. There is always a particular way of solving problems in each language, not exactly a way, but a preferable choice of writing the code if there exist more than one way of achieving something. And probably, this is the point where I lack, so if you find something wrong, please notify me or push a commit to [myrepo](https://github.com/PiyushDeshmukh/tnslip). So here is how you can make lists so that you can use it further in your code.


```python
squares = [i*i for i in range(20)]                          # squares of non-negative numbers upto 19
squaresgt10 = [i*i for i in range(20) if i > 10]            # squares of numbers [11, 20)
matrix = [[True for col in range(4)] for row in range(5)]   # 5by4 matrix with all values True
print(squares)
print(squaresgt10)
print(matrix)
```

    [0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100, 121, 144, 169, 196, 225, 256, 289, 324, 361]
    [121, 144, 169, 196, 225, 256, 289, 324, 361]
    [[True, True, True, True], [True, True, True, True], [True, True, True, True], [True, True, True, True], [True, True, True, True]]


In this way, you can have one liner for generating lists, that too which is pretty clear to read and understand. When it comes to readaibility, its always a good idea to divide your code into logical modules(or may be I mean functions here). This means that particular group of lines does some particular stuff, which is logically separated from other group of lines. The implementation of this(phenomenon generally termed as modularity) is done by using functions. On a bigger scale, we can talk about dedicating a class, or a module(analogous to package or library) in the same way, so that a complex functionality is broken down to some short pieces of code, again to enhance the readability and making it less mess for programmers to work with complex systems.

Functions are declared using `def` keyword, and as usual, the body is indented. Functions can take parameters, but are not mandatory. Functions can return a value. The moment a function returns a value, its execution stops and the corresponding values on the stack are erased. Hence, all the variables in function scope turn out of existence.


```python
def fizzbuzz(n):
    for i in range(n):
        print("Fizz"*(i%3 == 0) + " "*(i%15 == 0) + "Buzz"*(i%5 == 0) or str(i))
    return "Done"

if __name__ == '__main__':
    print("This is fizzbuzz test")
    result = fizzbuzz(20)
    print(result)
```

    This is fizzbuzz test
    Fizz Buzz
    1
    2
    Fizz
    4
    Buzz
    Fizz
    7
    8
    Fizz
    Buzz
    11
    Fizz
    13
    14
    Fizz Buzz
    16
    17
    Fizz
    19
    Done


The good thing about python is that you can change the sequence of arguments passed if you mention them explicitly during the call.


```python
def tell_me_about_language(name, designer, extension = None):
    print(name + " was designed by " + designer + " and is stored in a " + extension + " file.")

tell_me_about_language("Python", "Guido Van Rossum", ".py")
tell_me_about_language("Javascript", extension = ".js", designer = "Brendan Eich")
```

    Python was designed by Guido Van Rossum and is stored in a .py file.
    Javascript was designed by Brendan Eich and is stored in a .js file.


This feature is good to use when you have a large number of arguments available to pass to the function.

We can also pass indefinite number of arguments, and get them all in a list. This can be done by appending `*` before the variable name.


```python
def tell_me_about_language(name, *influenced):
    print(name + " has influenced " + ", ".join(influenced) + ".")

tell_me_about_language("Python", "CoffeeScript", "D", "Go", "Ruby", "Swift")
```

    Python has influenced CoffeeScript, D, Go, Ruby, Swift


Lets get more crazy, what if we want to know what keyword was used while passing the parameters? This is where you can append a double asterisk `**` to the variable name, and have a dictionary with keywords as keys and correspoding arguments as the values.


```python
def tell_me_about_language(name, **details):
    print(name + " is a good language!")
    print("It was designed by " + details["designer"] + ", and is " + details["paradigm"] + " language.")

tell_me_about_language("C", designer = "Dennis Ritchie", extension = ".c", paradigm = "imperative")
```

    C is a good language!
    It was designed by Dennis Ritchie, and is imperative


In python, arguments are passed by assignment. Its straightforward that you cannot change the values of immutable objects passed as arguments, however, in case of mutable objects you can modify the values and this modification will reflect outside the function scope unless you do a rebinding of that variable inside the function as it is obvious that the outer scope will be aware of nothing.

Another interesting feature of python is that it allows you to pause and resume the execution of a function. Such a construct is rather termed  as generator. A generator is differentaited from a function from the keyword `yield`. The `yield` statement basically allows you to pause the execution of a function by returning a value to the calling statement. Then the control flow goes as usual unless the function is called again. This time, when the function is called, the function resumes its execution from the statement right next where it paused earlier, and then continues the execution unless it encounters the next yield statement. It should be noted that the variables in the function scope retain their latest values everytime. So if a variable has been modified earlier, then its modiffied value is available to us everytime we call the function (and ofc unless we modify it again).

This is how we can get a fibonacci series from a generator.


```python
def fib(n):
    first = 0
    second = 1
    yield second
    for i in range(n-1):
        first, second = second, first + second
        yield second

print(fib(7))
for num in fib(7):
    print(num)
```

    <generator object fib at 0x7f52fd84a5a0>
    1
    1
    2
    3
    5
    8
    13


As shown above, a call to a generator yields a generator object. However, in order to use it, one of the best practices is to use it as an iterator from a `for` loop. The `for` loop is again special in this sense because it automatically calls the next execution of the generator everytime it tends to make a new iteration.

Generators become handy in cases when you want to consume less memory. For instance, if you call the `fib()` function to return many fibonacci numbers, like greater than a million, you obviously don't want it to return a list, as it shall make a huge memory consumption, instead you find for something that can return you the next fibonacci number whenever required on the fly, this way you can perform even better in terms of memory. This can easily be achieved with the help of generators, however, you get a drawback of this. As there is always a tradeoff, you pay for time when you attempt to reduce memory consumption. The same goes with the use of generators where you pay for speed because everytime you demand for the next returned value, the execution of the generator is resumed and carried out. Therefore, before it can continue executing current instructions, your CPU executes the instructions inside the generator to obtain the next value demanded dynamically. Later when it encounters the `yield` statement, it continues the execution from just after where the call was made.

So now the question comes, how often do we use generators in real life? And the answer is Frequently! Did you remember the `range()` function we discussed earlier? My apologies, I cheated there! It isn't a function, it is a generator!

The truth is, we have 2 things in python2, first is the `range()` which is a function, and second is the `xrange()` which is a generator. But when we move to python3, `xrange()` has been removed, and `range()` exists as a generator.


Besides `range()`, There are several [built-in](https://docs.python.org/3/library/functions.html) functions, which we will see whenever necessary.

## abouttheauthor

I am Piyush Deshmukh, I am an undergrad student from India. What drives me to write this article is my passion towards learning and my love for python(3). I have been programming since my high school. Please visit my [profile](https://piyushdeshmukh.github.io) if you want to be in touch.
