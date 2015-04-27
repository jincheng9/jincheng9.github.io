---
layout: post
title: "python syntax reference"
description: ""
category: [Python]
tags: []
---
{% include JB/setup %}
### 1. Five Standard Data Types and Operations
* Numbers (immutable)
	* int (signed integers)
	* long (long integers)
	* float (floating point real values)
	* complex (complex numbers)
{% highlight python linenos%}
var = 10
var = 10L
var = 10.0
var = 10+10j
{% endhighlight %}
		
* Bool (immutable)

{% highlight python linenos%}
a = True
b = False
{% endhighlight %}
	
* String (single quotation, double quotation, and triple quotation) (immutable)

	Triple quotation (''' or """) can be used to span the string into multiple lines. 
{% highlight python linenos%}
word = 'word'
sentence = "This is a sentence."
paragraph = """This is a paragraph. It is
	
made up of multiple lines and sentences."""
{% endhighlight %}
	
{% highlight python linenos%}
str = "hello world!"
print str
print str[0] # the first character
print str[1:3] # start from index 1, end at index 2
print str[1:] # start from index 1
print str*2 # repeat str 2 times
print str+'test' # concatenate str and 'test'
{% endhighlight %}
	
* List (like an array, but its elements can be different data types) (mutable)

{% highlight python linenos%}
list = [1, 'abc']
tinylist = [2, 'test']

print list
print list[0]  # the first element in list, data type is int
print list[1:2] # the second element in list, data type is List
print list[1:] # data type is List
print list*2 # [1, 'abc', 1, 'abc']
print list+tinylist # [1, 'abc', 2, 'test']
{% endhighlight %}
	
* Tuple (like a read-only list, it cannot be updated after initialization) (immutable)
{% highlight python linenos%}
tuple = (1, 'abc')
tinytuple = (2, 'test')

print tuple
print tuple[0]
print tuple[1:2]
pritn tuple[1:]
print tuple*2
print tuple+tinytuple
{% endhighlight %}
	
	Following is invalid with tuple.
	
{% highlight python linenos%}
tuple = ('abcd', 786 , 2.23, 'john', 70.2)
list = ['abcd', 786 , 2.23, 'john', 70.2]
tuple[2] = 1000    # Invalid syntax with tuple
list[2] = 1000     # Valid syntax with list
{% endhighlight %}
	
* Dictionary (mutable)

	Python's dictionaries are kind of hash table type that associates a key with a value. Key should be immutalbe data type.
	
{% highlight python linenos%}
dict = {}
dict['one'] = 'This is one'
dict[2] = "This is two"

tinydict = {'name': 'john', 'code':6734, 'dept':'sales'}

print dict['one'] # print the value for key 'one'
print dict[2] # print the value for key 2
print tinydict # print the dictionary
print tinydict.keys() # print all the keys, tinydict.keys() returns a list
print tinydict.values() # print all the values, tinydict.values() returns a list
{% endhighlight %}
	
	
### 2. Flow control

{% highlight python linenos%}
if condition1:
	statement1
elif condition2:
	statement2:
elif condition3:
	statement3:
else:
	statement4
{% endhighlight %}

{% highlight python linenos%}
for element in list:
	statement
{% endhighlight %}

{% highlight python linenos%}
while condition:
	statement
{% endhighlight %}

### 3. Function
{% highlight python linenos%}
def add(a, b):
	return a+b
{% endhighlight %}
	
### 4. Class and Object

	Objects of the same class share mutable class property, but have their own immutable class property and self property.
	
{% highlight python linenos%}
class Human(object):
	can_walk = True
	can_eat = True
	def __init__(self, play):
		self.play = play
	def show_walk(self):
		if self.can_walk:
			print 'Human can walk'
	def show_eat(self):
		if self.can_eat:
			print 'Human can eat'
			

peter = Human('football')
peter.show_walk()
peter.show_eat()
{% endhighlight %}
	
### 5. File Read and Write
{% highlight python linenos%}
f = open('test.txt', r)
content = f.readline()

for line in open('test.txt'):
	print line
{% endhighlight %}
	
### 6. Module in Python
	
{% highlight python linenos%}
import math
math.log10(10)

from math import log10
log10(10)

from math import *
log10(10)

import math as a
a.log10(10)

import thisdir.module #__init__.py should be in the directory of thisdir
{% endhighlight %}
	
### 7. Exception Handling

try -> exception happens -> corresponding exception handling block -> finally
try -> no exception -> else -> finally
When a return, break or continue statement is exceuted in the try suite of a try...finally statement, 
the finally clause is also executed "on the way out".

{% highlight python linenos%}
try:
	statement
except exception1:
	statement
except exception2:
	statement
except exception3:
	statement
except:
	statement
else:
	statement
finally:
	statement
{% endhighlight %}

We can raise exception if needed.
{%highlight python linenos %}
print 'lalalatest'
raise StopIteration
print 'hahaha'
{% endhighlight %}
