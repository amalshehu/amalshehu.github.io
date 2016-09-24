---
layout: post
title:  "Python Clock"
date:   2016-09-24
excerpt: "Clock problem exercism"
tag:
- python
- Exercism
- clock
comments: true
---

## Clock Problem Explained(exercism.io):
Implement a clock that handles times without dates.

Create a clock that is independent of date.

You should be able to add and subtract minutes to it.

Two clocks that represent the same time should be equal to each other.


* `Print time HH:MM`
*  `"+" or "-" Minutes`
* `Independent of date`
* `Military format`
* `Compare two clocks`
* `Add minutes`

## Source

Pairing session with Erin Drummond [https://twitter.com/ebdrummond](https://twitter.com/ebdrummond)

## Solution
~~~~ruby
class Clock:

    _objecx = []
~~~~
The `_objecx` member variable will store all the initialized clock objects.
~~~~ruby
def __new__(cls, hour, minute):
      for objec in _objecx:
          if cls.obj == objec:
              return objec
      return cls.obj
~~~~
Use `__new__` when you need to control the creation of a new instance.
`__new__` is the first step of instance creation.
It's called first, and is responsible for returning a new instance of your class.
In general, you shouldn't need to override `__new__` unless you're subclassing an immutable type like str, int, unicode or tuple.
Here creates new clock if not already exist.


~~~~ruby
def __init__(self, hour, minute):

      self.hour = (hour + (minute // 60)) % 24
      self.minute = minute % 60
~~~~
Use `__init__` when you need to control initialization of a new instance.
In contrast, `__init__` doesn't return anything; it's only responsible for initializing the instance after it's been created.
The clock time formatted and initialized object.

~~~~ruby

def __eq__(self, another):
      return self.hour == another.hour and self.minute == another.minute
~~~~
 If you want your custom objects to be only comparable for equality with other objects, then you can provide the `__eq__` methord.
Comparing two clocks and equalize.

~~~~ruby

def __str__(self):
      return "{0:02d}:{1:02d}".format(self.hour, self.minute)
~~~~
Python has two different ways to convert an object to a string: str() and repr().
Printing an object uses str(); printing a list containing an object uses str() for the list itself, but the implementation of list.
`__str__()` calls `repr()` for the individual items.
 Python3 string formatting function.`'{:02d}:{:02d}'` - 0 is first digit, 2 digits, d is for integer format.

~~~~ruby
def add(self, minute_x):
      return Clock(self.hour, self.minute + minute_x)

~~~~
Defined the `__add__` method in `Clock` class to perform vector addition and then the plus operator would behave as per expectation.




### Inspirational quote

> The mark of a mature programmer is willingness to throw out code you spent time on when you realize it's pointless. -Bram Cohen
