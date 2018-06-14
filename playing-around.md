---
description: >-
  The following lesson takes us through an Interactive journey where we will
  actually talk and give instructions to our IoT development board and observe
  the output instantly.
---

# Getting Superpowers

> "Having an idea and then programming it on a computer to see it in your hands and then press a button to be able to see in millions of people's hand. It is the closest thing that we have to a Superpower today"
>
> -- Drew Houston\(Creator of Dropbox\)

{% embed data="{\"url\":\"https://youtu.be/nKIu9yen5nc\",\"type\":\"video\",\"title\":\"What Most Schools Don\'t Teach\",\"description\":\"Learn about a new \\\"superpower\\\" that isn\'t being taught in 90% of US schools. \\n\\nStarring Bill Gates, Mark Zuckerberg, will.i.am, Chris Bosh, Jack Dorsey, Tony Hsieh, Drew Houston, Gabe Newell, Ruchi Sanghvi, Elena Silenok, Vanessa Hurst, and Hadi Partovi. Directed by Lesley Chilcott, executive producers Hadi and Ali Partovi.\\n\\nCode.org owes special thanks to all the cast and the film crew, and also Microsoft, Google/YouTube, Facebook, Amazon, and Twitter for helping us spread the word\\n\\n\(If you want to help translate to other languages, visit http://www.code.org/translate\)\\n\\nHelp us caption & translate this video!\\n\\nhttps://amara.org/v/BeyV/\",\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://i.ytimg.com/vi/nKIu9yen5nc/mqdefault.jpg\",\"width\":320,\"height\":180,\"aspectRatio\":0.5625},\"embed\":{\"type\":\"player\",\"url\":\"https://www.youtube.com/embed/nKIu9yen5nc?rel=0&showinfo=0\",\"html\":\"<div style=\\\"left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.2493%;\\\"><iframe src=\\\"https://www.youtube.com/embed/nKIu9yen5nc?rel=0&amp;showinfo=0\\\" style=\\\"border: 0; top: 0; left: 0; width: 100%; height: 100%; position: absolute;\\\" allowfullscreen scrolling=\\\"no\\\"></iframe></div>\",\"aspectRatio\":1.7778},\"caption\":\"What Most School\'s Don\'t Teach?\"}" %}

## Just playing around

Becoming a super-hero is a fairly straight forward process: 

> Stop learning by reading alone. Instead, let's start experiencing it!

### Saying Hello

In the MicroPython firmware, there is an in-built Interpreter to evaluate whatever instructions we pass on to it. Open Putty and load your saved session to open the MicroPython REPL prompt `>>>`    

The instruction can be as simple as printing your name on the screen, for example:

{% code-tabs %}
{% code-tabs-item title="Printing" %}
```text
>>> print('Python is amazing!')
```
{% endcode-tabs-item %}
{% endcode-tabs %}

**Out\[ \]** - `Python is amazing!` 

As you can see the output contains the string of characters included within single-quotes of the `print()` function.

{% code-tabs %}
{% code-tabs-item title="Mathematics.py" %}
```text
>>>20*100
>>>8.9*6.7
59.63
>>>2.2*3*7.4*2
194.04000000000002
>>>9.7/6
1.6166666666666665
>>>999/3
333.0
>>>3+9
12
>>>809755+123781238
124590993
>>>7.08797+213123123.4374
213123130.52537
>>>1-23.0978
-22.0978
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Also, in the above program named _Mathematics.py,_ we can see that calculations returns some output. 

If we wish to use this data somewhere in the program, we need to store it somewhere in the Computer's memory and assign a name to it for later use.

In terms of Computation, such memory location names are called "Variables" that are used specifically for saving data of any type. But for Python, the entire process of assigning different `data-types`  is automated, unlike other popular programming languages like C, C++ and Java.

The Python Interpreter itself checks what type of data is passed into the variable. Now let us take an integer value and store it in a variable.

{% code-tabs %}
{% code-tabs-item title="variables" %}
```text
number1 = 333
number2 = 23.333
name = "me, myself and I"
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Here, we are saving an Integer value to the variable named `variable` with no information from us about what type of data it is. Look at the intelligence of the language and simplicity as well, it can detect whether the input is Integers, Strings, Characters, Decimal\(floating-point\) numbers, etc.  
  
In order to know what `data-type` a variable possesses, do this:

{% code-tabs %}
{% code-tabs-item title="dataTypes" %}
```text
>>>type(number2)
<class 'float'>
>>>type(number1)
<class 'int'>
>>>type(name)
<class 'str'>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

 

{% code-tabs %}
{% code-tabs-item title="calling a variable" %}
```text
>>>number1
333
>>>name
me, myself and I
>>>number2
23.333
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Simple, isn't it?



