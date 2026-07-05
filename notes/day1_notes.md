# Day 1 (Basics revision)

**Date learned:** 2026-07-04 

## I am gonna relearn the basics of python using C language as a comparison
## Variables
1. In python variables act like references. a = 5 acts like a pointer in C but in Python is just a name/reference to the object
Unlike C in python i cant do pointer arithmetics like (a+1) to "move" and see what is stored next to a.
I cant use * or &, there is no double pointer ** and i cant control the memory by myself, GC handles it. 

2. No need to declare type like int x = 5. x = 5 is enough and i can even do x = 5 and then x = "string" without any bugs. 
(Remember it acts like a pointer)
(There are type hints but its just for you to see the compiler kinda ignores them (If there was one :P))
(Well Python doesnt have a compiler like C does. It has an intepreter that is functionally different than a compiler)

3. Mutable vs Immutable. Whenever i change something like x = "string" x += "added this" it will either change the item itself Mutable or 
create a brand new object Immutable. The strings (str) are Immutable so it will create a new string with the addition i made leaving the old one
untouched. If the old str is left with no reference showing at it the Python Garbage Collector will take over to free up space. 

Easy example to test in real time if a certain variable is Mutable or not:

x = "string"
print(id(x))

x += "addition"
print(id(x))

Different id = different object = Immutable. Else its the same object thus the variable is Mutable. 

4. a = b wont copy the varible b into a but the address of it making it that both a and b show at the same item. 
To fix that i can import copy and then i can shallow and deep copy. The shallow copy funtcion a = b.copy() will copy the container b but the variables inside it 
will be common to both a and b. The deepcopy a = copy.deepcopy(a) is more like a physical copy that you end up having 2 completly different items. 

## Data structures

The bult-in data structures i will revise first are list, tuple, dict, set.

The idea is that:
1. If i care about the order of insertion, need duplicates, will change the structure -> I use list
2. If i want something Immutable able to hash (with hashable contents), return multiple variables -> I use tuple
3. If i need to lookup things with a key like: age, name etc -> I use dict
4. If i dont care about multiples, need fast search O(1) and want to do set opperations -> I use set

Lets dive in into each one of those data structures. 

## list

First of all i can add in it any type of data. I can even do :
xs = [10, 20, 30, "mix", [1, 2]] 

```python


xs.append(x)        # add x in the end of xs        O(1)
xs.insert(i, x)     # Add x in the position of i    O(n)
xs.extend([a, b])   # Add multiple elements
xs.remove(x)        # Remove the first x in xs      O(n)
xs.pop()            # removes the last element and returns it
xs.pop(i)           # removes the ith item and returns it
xs.sort()           # sorts in-place
len(xs)             # returns the length of xs list
x in xs             # checks if xs contains a x               O(n) <-- Way slower than O(1) of a set


```

## tuple

The Immutable list. Trying to change it like point[0] = 9  will end up in TypeError!
Fuctions that return multiple things use tuple like return a,b. That will return a tuple. 
It is like a const struct in C.

## dict
The main use/idea behind dict is that i can search it using a key rather than a value

```python

user = {"name": "Anna", "age": 30, "active": True}
user["name"]           # "Anna"
user["missing"]        # KeyError!
user.get("missing")    # None  Proper way to search it if you arent sure what it contains beforehand
user.get("x", 0)       # 0     

# to alter it, use it properly there are the following actions

user["email"] = "a@b.c"    # O(1) to add or change the value of a key
del user["age"]            # delete key
"name" in user             # O(1) to check the a key
user.keys()                # all the keys
user.values()              # all the values
user.items()               # The pairs key-value assigned to it

for k, v in user.items():  # for used for iteration
    print(k, v)

```


## set

The main idea of a set is to stop caring about the order and just care if a value is in the set. 

```python

s = {1, 2, 3}
s = set()          # make an empty set
s = set([1, 1, 2]) # equals to {1, 2}  -- It will automatically ignore the second 1 itself and up being {1, 2}

# Main ways to add update discard and remove values out of it
s.add(x)           # O(1)
s.update([a, b])   # update actually means to add multiple at once and be treated like making multiple adds at once
s.discard(x)       # proper way to remove
s.remove(x)        # this can lead to Keyerror if x value isnt in the set
x in s             # O(1) to check if x is in s. * for comparison in a list it is O(n)
len(s)

# Basic mathematical operations

a = {1, 2, 3}
b = {2, 3, 4}
a & b      # {2, 3} intersection 
a | b      # {1, 2, 3, 4} union 
a - b      # {1} difference 
a ^ b      # {1, 4} symmetric difference

```

A sumary to how i make each one of list, tuple, dict, set.

```python

xs = [1, 2, 3]         # list
xs = list([1, 2, 3])       # same as the one with []

t = (1, 2, 3)          # tuple
t = 1, 2, 3            # even without () its a tuple
t = tuple([1, 2, 3])   # same as the other ones

d = {"name": "Anna", "age": 30}   # dict — just because there is the symbol :
d = dict(name="Anna", age=30)     # alternative way with keyword args

s = {1, 2, 3}          # set 
s = set([1, 2, 3])     # same set as {1, 2, 3} 
s = set([1, 2, 2])     # will equal to {1, 2}
s = set(1, 2, 2)       # will return an error same as list and tuple without []


print(type(x))    # can always do this to check the type of each one


```
