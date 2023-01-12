# Python from Scratch - How to Write a Computer Program.

## Setup

This is a lesson on how to write a computer program. We are going to be doing this using the language Python, which according to [one of the industry's biggest surveys](https://survey.stackoverflow.co/2022/#section-most-popular-technologies-programming-scripting-and-markup-languages) was the fourth most widely used programming language in the world in 2022, and the most popular language that isn't specialized for databases or webpages. It's very approachable. It was named after the British comedy group Monty Python who made movies like the one about the Holy Grail. We're going to use it to write a computer program. Does everyone have Python?

It is available at https://www.python.org/downloads/. I am using the latest version, Python 3.11, but any version that starts with "3" should be fine.

I don't want to dwell on getting everyone to set up fancy coding and editing software, so I'm going ask everyone to create a super basic setup for this. Make a new folder on your computer, called something like "fun_programs". Open up a plain text editor such as Notepad or TextEdit and save a new file in that folder called `inventory.py`. Then, open a terminal window in that folder.

Windows has two terminal applications: an old one called CMD and a new one called PowerShell. You might as well get with the times and use PowerShell. To open it, just hold shift and right click in the blank space in a folder and click the "Open PowerShell window here" option in the menu that appears. Or, use the menu in the top left corner of File Explorer:

![](images/file-explorer-powershell.png)

Mac OS X has one terminal application. It is called "Terminal." You are going to need to open it and then switch what folder is open in it. To do that, open the Terminal, type the letters "cd" and then a space, and then drag the folder you're working with from the Finder into the terminal window. Then hit enter. (cd stands for "change directory.")

If you're on Linux, I'm assuming you know what you're doing. Good luck, or ask someone else here and see what happens.

Programmers like to run programs by typing the programs' names into command lines instead of double-clicking on icons for them because it's easier to specify options and automate things that way. This is how we're going to run our Python programs, but also, pretty much any program that you write can be executed using the command line; you can compile and run the C++ programs that you write in university CS classes using the same basic method. We're going to write a program here in the text editor that you opened. It will look like this:

```python
print("Hello, World!")
```

Write that, and then save it. Then, leave the text editor open, but run your new program in the command line by typing `python inventory.py`. (If you're on a Linux operating system that previously used old versions of Python, you might have to specify the version you want by using `python3 inventory.py` instead.)

Did that work? If it did: great! The boring part is over. Now we can start programming. The hardest part of running Python programs is often the setup, even in this case where it's a really simple one.

## Variables and strings

You may have noticed that we have now written a computer program. It outputs the words "Hello, World" into the command line in which it was run. The word "print" in computer programming actually means "output this text to the command line;" it used to involve printers, but since then, screens have been invented. The punctuation requirements here are pretty specific: you have to have the word "print", an open parenthesis, a quotation mark, some text, a closing quotation mark, and a closing parenthesis. All of this punctuation is part of an understandable system: I promise. And now we can start to pull it apart and understand how it works.

We've technically written a computer program, but it's not a very impressive one. Let's assume, for the sake of argument, that I have a large collection of gamer mice. It is so large that I need to be able to store them in a computer program and then search through them. A lot of computer programs, like inventory systems or library catalogs, basically exist just to store items and search through them. 

To start storing mice in my program, I'm going to create my first variable. You're probably vaguely familiar with the concept of variables from algebra. In programming, we don't really solve for them, we use them in a very straightforward way: we pick a variable name, like "mouse", and we store some data under it.

```python
mouse = "Logitech G502 HERO SE"
```

If you put some text in quotation marks, you create a string, which is text-based data that you can have in a program. The quotation marks mean, "this text is here purely to be used as data; it does not contain commands or instructions or stuff the program needs to do." Equals signs assign data to variable names. You probably get the idea. Now, I want to change the print statement. Instead of printing out Hello, World, I want to print the name of my mouse. I can do that without retyping the mouse's name by using the variable like this:

```python
print(mouse)
```

Run this program on the command line by typing `python inventory.py` (or maybe `python3 inventory.py`.) As you can see, whereas before we were printing a string, we are now printing a variable, and we are getting the string that was stored in that variable. In general, variable names give you a way to refer to data without writing all the data out; you can think of them as being automatically replaced by that data behind the scenes. Change it to something random and try again:

```python
mouse = "Chuck E. Cheese"
print(mouse)
```

This works too. Really, after all, what is Chuck E. Cheese, if not a gamer mouse?

## Lists and for loops

Now, if I'm going to store a collection of things in a program, I want it to be able to grow to an arbitrary size. One obvious approach to store multiple mice would be to make variables called mouse1, then mouse2, then mouse3, but fundamentally that would be really tedious and limit you in the amount of mice that you could store. Instead, we're going to make a list, which will let us store an arbitrary number of separate strings in a single variable. The list is a fundamental data structure in Python and you will not get far without it.

```python
mice = ["Logitech G502 HERO SE", "Chuck E. Cheese", "Razer Basilisk X"]
```

You might reasonably ask: those square brackets look important, but how is this really different from making one long string with all the names in it? It turns out that lists bring up a lot of possibilities. For example, you can select items from them by their position in the list, which is called their index:

```python
print(mice[1])
```

This prints the middle item in this list because items in lists in programming are numbered starting from 0, so the items we have here are numbered 0, 1, and 2. We've also unlocked an important programming ability, which is the chance to do something over and over again with a structure called a loop:

```python
for mouse in mice:
    print("This is a mouse:")
    print(mouse)
```

This kind of loop is called a "for loop", and the idea is that it does something once for each item in a list. The first line kind of announces the loop; you use the keywords "for" and "in" and alongside them, you put the variable that's storing your list, and also, before that, a new variable name that will be used for each item in the list. For each of the values in that list, the lines of code that are indented will be run, with each successive list item available under the new variable name, "mouse", within them. (You can indent lines by pressing tab on your keyboard in front of them.)

## Built-in functions and numbers

We've explored quotation marks, commas, square brackets, and the magic words "for" and "in". Now we finally have to talk about the parentheses. Parentheses are used to invoke functions, which are basic reusable pieces of code. Python provides for us a function called "print" that does the boring but important work of sending text to the command line. By putting parentheses after this function name, you are calling or invoking the function, and you can give it some bonus information about what you want it to do by putting some kind of input inside the parentheses. In this case, when we call "print", we want to tell it what to print in that way.

There are other built-in functions. For example:

```python
number_of_mice = len(mice)
print(number_of_mice)
```

"len" is the abbreviated form of the word "length" and, when called as a function with our list of mice as its input, it will tell us how long our list is. When functions give us information, it's called "returning" something, and you can imagine that the code `len(mice)` disappears and is replaced by the data the function ends up returning; in this case, the number 3.

*The below math content and extra built-in functions could be cut for time*

By the way, did you know that you can store numbers in variables? Those are different from strings. You can do math with them.

```python
number_of_mice = len(mice)
print(number_of_mice + 2)
```

I don't know why you would want to do that specifically! But the point is, when a variable stores a number you can use it for math. (When it stores a string, not so much.) Pretty much any mathematical expression that you can type into a calculator, you can type into a programming language, and in the programming language you can use variable names when you want to use values that a program has previously stored. Just like how a function call disappears and is replaced with its result, mathematical expressions just sort of disappear when the program runs and are replaced by their answer.

There are more built-in functions in Python. Watch this:

```python
number_of_mice = len(mice)
mice_squared = pow(number_of_mice, 2)
print(mice_squared)
```

Look at that! I don't know why you would want to do this either, but you can raise a number to the power of 2 (or anything else) with the `pow` function, store the result in a variable, and print that out. Notice that this function, the `pow` function, takes two different values as inputs, separated by commas. They both have to be numbers, and it will return the first raised to the power of the second. Now watch this.

```python
print(min(number_of_mice, mice_squared))
print(max(number_of_mice, mice_squared))
```

`min` is a function that takes two inputs and returns whichever is smaller. `max` is a function that does the same thing but returns whichever is larger. Also, look: I am putting function calls inside of function calls. When you do this, the results are evaluated from the inside out. On the inside, the call to max is basically replaced with its result, and then the call the print happens with that as its input. You can imagine the whole thing, `max(number_of_mice, mice_squared)` being replaced by the number 9, because that's the larger number: `print(max(number_of_mice, mice_squared))` becomes just `print(9)`.

## User input

The problem is, it's too easy to figure out what the results of these function calls will be, because the values stored in the variables are completely predictable. To write a real computer program, we want them to change over time. To do this, let's create a new variable and learn one more function call that will completely change what our program is capable of.

```python
new_mouse = input("Enter a mouse name:")
print("You entered:")
print(new_mouse)
```

This new function, "input", initially seems to act like the print function, but there's something else that happens after your string is printed out: it collects some text from the command line and returns it so that text can be stored in a variable. To see this, you have to type the text into the prompt at the command line and then hit enter. So when I run the program and type Wolfgang Amadeus Mousezart, that string goes inside the program and can be referred to with a variable. We can take this one step further:

```python
new_mouse = input("Enter a mouse name: ")
mice.append(new_mouse)
print(mice)
```

There are two basic types of functions in Python: those that are free-floating and those that are part of a particular data structure. The functions we've been using up to this point are free-floating functions that operate on single values; however, a list is an example of a data structure and lists have lots of member functions that are list functions that are specific to lists. For example: the member function "append". To access a member function, take a data structure, put a dot after it, put the name of the function, and then call it with parentheses and usually an input.

I say usually an input. Strings are data structures too, and they have lots of fun member functions that don't happen to need any input.

```python
print(new_mouse.lower())
print(new_mouse.upper())
```

Structures that package functions and data together like strings and lists do are usually called objects.

## Conditions: while loops and if statements

*This whole section could be cut for time; if statements would then be introduced under "Custom functions"*

Objects are a whole extra can of worms, so let's go back to making our variables less predictable. Replace the line `mice.append(new_mouse)` in that earlier code with this:

```python
new_mouse = input("Enter a mouse name: ")
while new_mouse != "quit":
    mice.append(new_mouse)
    new_mouse = input("Enter a mouse name: ")
```

This is a while loop. Like a for loop, it will run some indented code over and over. Unlike a for loop, it can run indefinitely, instead of just activating once for each item in a list. In the first line of our while loop, which has to use the keyword "while", we have the symbols exclamation mark and equals. Together, these two symbols mean "does not equal." With that in mind, you can read this kind of like English: while the variable new_mouse does not equal the string "quit", run these indented lines of code. This loop would run forever if we had no opportunity to modify the value stored by `new_mouse`, but luckily we do: over and over again, the result of the call to the "input" function will be assigned to it.

In other words, this code will first ask us to enter a mouse name. Then, it will start executing the code that's indented under the while loop (unless we typed "quit" to begin with; while loops do not always get the chance to even run once.) In so doing, it will append that new mouse name to the list "mice" and then ask us for another new mouse name. These last two steps will repeat (in a \*loop*) until new_mouse is equal to the string "quit" because we typed "quit" into the command prompt. This allows us to enter and store an indefinite number of mice and then stop when we want to.

If your while loop ever tries to run away with your program and starts running over and over again, click in the console and press Control-C to stop it, and then take a look at the code again.

The ability to do things over and over again an arbitrary number of times is very important and useful, and our code is getting more like a real program by the second. However, there is one problem. If I were to do something dumb like just hit enter a bunch of times when it asked me to input a mouse name, the result would be a bunch of empty strings in the `mice` list. That's right: it turns out that strings can be empty and store zero characters. To prevent that, we can set up a guardrail with an if statement:

```python
while new_mouse != "quit":
    if len(new_mouse) > 0:
        mice.append(new_mouse)
    else:
        print("name too short >:(")
    new_mouse = input("Enter a mouse name: ")
```

This code uses the magic words "if" and "else" and the function "len" that we looked at before. That's right: it turns out that strings have lengths just like lists do, and you can use the same function to get them. An if-else statement will run some indented code if some certain logical condition is true: in this case, if the length of the new mouse's name is greater than 0. Otherwise, it will run some different code, which needs to appear below a line that just says "else:"; in this case, we're printing an error message to the program's user. Which is you in this case, but could be someone else in other contexts.

Note that this is different from the condition in the while loop because we're not stopping the whole process based on it; we're printing an error message if what we want to be true isn't true, but the loop will still continue, so the user can try again. Aside from that, though, the types of conditions that can be used in while loops, in if statements, and in other places are all the same, and we could use a while loop with a greater-than symbol or an if statement with a not-equal-to symbol if we wanted.

So, we now have the ability to enter into our computer the names of infinite mice.

## Custom functions

We are halfway to having a program that can store a catalog of mouse names and search through them. To do this, I'm actually going to switch to a new file that isn't going to ask me to enter names every time I run it: for demonstration purposes, I'm going to work with a static list of mouse names. This is basically just cheating to avoid entering them all into the command line.

```python
mice = ["Logitech G502 HERO SE", "Logitech MS Master 3S", "Tailer Swift", "Anonymouse", "Hatsune Squeaku"]
```

Now, we want to implement search functionality; to do this, we are going to define a custom function called `search_for`. To define a function, you write the keyword "def", the name you're giving to the function, and then parentheses with a list of the input variables you want the function to have (in this case only one). The input variables consist of things you want to potentially change every time the function is run; otherwise, you can use the so-called global variables from outside the function normally, although doing that too much can get a little bit disorganized.

```python
def search_for(search_term):
```

This input variable `search_term`, which is called a parameter, doesn't have any intrinsic value. However, when the function is called, it will be given the value that is placed within the parentheses at that point in the code; it's basically a placeholder for now. Now we need an indented block of code that will actually run at the point at which the function is called.

```python
def search_for(search_term):
    for mouse in mice:
        if search_term == mouse:
            print("Found:")
            print(mouse)
```

We are approaching dangerous levels of indentation here, so let's break this down. All of the code that is part of the function and thus will run when it is called needs to be indented to indicate that it's part of the function. Then, we start a for loop; remember, this will set the new variable `mouse` equal to each successive item in our list `mice`. The code that is repeatedly run by the for loop has to be indented too, to indicate that it's inside the loop. Then we have an if statement, which specifies that the indented code below it will only run if a certain condition is true. In this case, the condition compares the parameter `search_term` to the loop variable `mouse` using the double equals sign operator, which looks for equality between the thing on the left and the thing on the right of it. (The single equals sign needs to be used only for assignment, not for comparison.) And the indented code under the if statement, which will be run if the condition is true, simply prints the loop variable `mouse` out.

Whew. We can now call this function with some inputs:

```python
search_for("Anonymouse")
```

The parameter `search_term` will take on the value of the string "Anonymouse", and that mouse will be found in the list and then printed out as the function runs with those variables. That's all very well, but it's very predictable since the search term string is baked right into the program. Let's try getting it from user input:

```python
term_from_input = input("Enter a search term: ")
search_for(term_from_input)
```

Now we're using something from user input as a search term, and it can be different every time. So that's cool. But the program is still kind of boring since we're getting out exactly what we're putting in. Let's make one small change to our `search_for` function:

```python
def search_for(search_term):
    for mouse in mice:
        if search_term in mouse:  # <-- in!
            print("Found:")
            print(mouse)
```

Now, instead of the `print` code running if the search term and the mouse name are equal, they will run if the search term is merely somewhere inside the mouse name. This means I can now just use "Logitech" as my input and get the full name of every Logitech mouse stored in the program.

So now, after much tumult and turmoil, we have a searchable database of mouse names.


