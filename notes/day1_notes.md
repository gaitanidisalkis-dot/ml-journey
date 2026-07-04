# Day 1 (Basics revision)

**Date learned:** 2026-07-04 

## I am gonna relearn the basics of python using C language as a comparison
## Variables
1. In python variables act like references. a = 5 acts like a pointer in C. It points to where 5 is stored.
Unlike C in python i cant do pointer arithmetics like (a+1) to "move" and see what is stored next to a.
I cant use * or &, there is no double pointer ** and i cant control the memory by myself, GC handles it. 

2. No need to declare type like int x = 5. x = 5 is enough and i can even do x = 5 and then x = "string" without any bugs. 
(Remember it acts like a pointer)
(There are type hints but its just for you to see the compiler kinda ignores them)

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
2. If i want something Immutable able to hash, return multiple variables -> I use tuple
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

## dict

## set