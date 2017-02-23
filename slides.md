% title: Python for beginners
% author: Jack Brookes
% author: PhD psychology student
% thankyou: Thank you
% contact: <span>email</span> <a href="mailto:ed11jb@leeds.ac.uk">ed11jb@leeds.ac.uk</a>
% contact: <span>github</span> <a href="http://github.com/jackbrookes">JackBrookes</a>
% favicon: http://www.leeds.ac.uk/site/img/other/favicon.ico


---
title: Contents
build_lists: true

- Background & Installation
- Basic Syntax
- Packages and Modules
- Resources

---
title: What is Python?
build_lists: true

- General purpose <a href="https://en.wikipedia.org/wiki/High-level_programming_language">high level</a> programming language
	- Syntax used to give instructions to a computer
	- Platform for re-using code developed by others
- Designed to be very '<a href="https://en.wikipedia.org/wiki/Python_(programming_language)#Features_and_philosophy">human readable</a>'

- <pre class="prettyprint" data-lang="python">
age = int(input('Please type your age in years: '))
if age > 20 and age < 35:
    print("You are eligible for this experiment")
else:
    print("Sorry, you are not eligible for this experiment")
</pre>


---
title: Why Python?
build_lists: true
class: img-top-center

- Easy to learn
- 'Stepping stone' into the programming universe
- Python is 'the second best at everything'
- <a href="http://www.itjobswatch.co.uk/jobs/england/python.do">Increasingly high demand and high pay</a>
- Used a lot in academia
- Very popular

---
title: What can I use Python for?
build_lists: true

- Data processing, visualisation & analysis
- Developing experiments (pygame, psychopy, OpenSesame, Expyrement)
- <a href="https://automatetheboringstuff.com/">Automation</a>, e.g.
	- Rename thousands of CSV files
	- Grab a user's tweets for language analysis
	- Perform automatic emotion recognition in a video
	- Mathematically model behaviour observed in your experiment
- Will help you understand other people's code

---
title: How do I use Python?
subtitle: Installation
build_lists: true

- Python 2 vs Python 3
- Many ways to install
	- Download from <a href="http://python.org">python.org</a>
	- Download <a href="https://www.continuum.io/downloads">Anaconda</a>
	- Download <a href="https://winpython.github.io/">WinPython</a> (my preference)
- Choice of IDE
	- IDLE
	- Spyder

---
title: How do I use Python?
subtitle: Writing code
class: img-top-center

<img src="figures/spyder.png"/ style="height: 480px;">


---
title: Word of warning

- Programming is hard
- The first hours of learning are frustrating
- Becomes logical when you understand
- Be curious
- Following code used as examples, use as a guide

---
title: Basic syntax
subtitle: Variables

Assign an object to a variable name with "="

<pre class="prettyprint" data-lang="python">
my_first_number = 23
my_second_number = 56
my_result = my_first_number + my_second_number
print(my_result)
</pre>

<p class="output">79</p>
- Names should be in snake_case
- Avoid <a href="http://pentangle.net/python/handbook/node52.html">some names</a>

---
title: Basic syntax
subtitle: Data types

Everything is an "object"

<pre class="prettyprint" data-lang="python">
my_bool = True
my_int = 32423456
my_float = 12.765
my_str = "hello" # <-- You can use ' or " for strings
my_list = ['Apple', 'Orange', 'Banana']
my_dictionary = {'Name': 'Jack', 'Age': 23}
my_text_stimulus = psychopy.visual.TextStim(my_window, text="Hello!")
</pre>

- Data type is not strict


---
title: Basic syntax
subtitle: Classes, functions, object

"Classes" are custom data types that have special properties
"Functions" are pre-written sections of code

<pre class="prettyprint" data-lang="python">
# CLASSES usually start with capital letters
# this is the creation of a "TextStim" object with some parameters
my_text_stimulus = psychopy.visual.TextStim(my_window, text="Hello!")

# FUNCTIONS are usually snake_case and are called with ()
# this is using "len" function, which returns the length of the object
my_number = len("something") # <-- my_number now equals 9

# dots are used for hierarchical grouping (special, unlike R)
my_new_object = some_module.some_object.some_function(my_parameter)
my_new_object = some_module.SomeClass(my_parameter)
</pre>


---
title: Basic syntax
subtitle: Comments

Help make your code easier to understand with "#"

<pre class="prettyprint" data-lang="python">
# ask for participant's age then store in "age_input"
age_input = input("Enter your age: ")
# convert their input from a string into an integer
age = int(age_input)
# show a message on the screen
print("You are {} years old!".format(age))
</pre>

<p class="output">
Enter your age: 23 <br>
You are 23 years old
</p>



---
title: Basic syntax
subtitle: Operations

<pre class="prettyprint" data-lang="python">
my_1st_num = 8
my_2nd_num = 7
my_result = my_1st_num * my_2nd_num
print(my_result)

my_1st_str = "Today it is: "
my_2nd_str = "Thursday"
my_result = my_1st_str + my_2nd_str
print(my_result)

print( "abc" * 10 )
</pre>
<p class="output">
56 <br>
Today it is: Thursday <br>
abcabcabcabcabcabcabcabcabcabc
</p>


---
title: Basic syntax
subtitle: Operations: Psychology example

4 trials of displaying text a stimulus, repeated x10

<pre class="prettyprint" data-lang="python">
my_text_list = ["heads", "shoulders", "knees", "toes"]
my_full_text_list = my_text_list * 10
print(my_full_text_list)
</pre>
<p class="output">
['heads', 'shoulders', 'knees', 'toes', 'heads', 'shoulders', 'knees', 'toes', 'heads', 'shoulders', 'knees', 'toes', 'heads', 'shoulders', 'knees', 'toes', 'heads', 'shoulders', 'knees', 'toes', 'heads', 'shoulders', 'knees', 'toes', 'heads', 'shoulders', 'knees', 'toes', 'heads', 'shoulders', 'knees', 'toes', 'heads', 'shoulders', 'knees', 'toes', 'heads', 'shoulders', 'knees', 'toes']
</p>

---
title: Basic syntax
subtitle: Operations (2)

<pre class="prettyprint" data-lang="python">
my_number = 10
print(my_number)
my_number += 5
print(my_number)
my_text = "Hello"
print(my_text)
my_text += "!"
print(my_text)
</pre>
<p class="output">
10<br>
15<br>
Hello<br>
Hello!
</p>


---
title: Basic syntax
subtitle: Lists

Store lots of objects in an order

<pre class="prettyprint" data-lang="python">
my_fav_colour = "Blue"
my_fav_cities = ["Leeds", "London"]
my_fav_number = 7
my_fav_things = [my_fav_colour, my_fav_cities, my_fav_number]
print(my_fav_things)
more_things = ["Python", 3.1412]
all_things = my_fav_things + more_things
print(all_things)
# get a particular element with square brackets
print(all_things[2])
</pre>
<p class="output">
['Blue', ['Leeds', 'London'], 7] <br>
['Blue', ['Leeds', 'London'], 7, 'Python', 3.1412] <br>
7
</p>

---
title: Basic syntax
subtitle: Dictionaries: Psychology example

Store objects in arbitrary order, but associated with a "key"

<pre class="prettyprint" data-lang="python">
# calculate reaction time & accuracy in some way
reaction_time = 0.659 # (for example)
accuracy = 89 # (for example)
# store results for this trial in a dictionary
trial_results = {"RT": reaction_time,
				 "ACC": accuracy}
print(trial_results)
# access using key name in square brackets
print(trial_results['ACC'])
</pre>
<p class="output">
{'RT': 0.659, 'ACC': 89}<br>
89
</p>


---
title: Basic syntax
subtitle: for loops

Perform an action a set number of times

<pre class="prettyprint" data-lang="python">
list_of_numbers = [1, 2, 3, 4]
for n in list_of_numbers:
	print(n*2)
print("Finished!")
</pre>
<p class="output">
2<br>
4<br>
6<br>
8<br>
Finished!
</p>


---
title: Basic syntax
subtitle: for loops: Psychology example

For a 200 trial experiment, don't copy-paste 200 times...

<pre class="prettyprint" data-lang="python">
number_of_trials = 200
for trial in range(number_of_trials):
	# (your code goes here)
	# show stimulus
	# wait for action
	# record result
	# repeat
</pre>



---
title: Basic syntax
subtitle: Boolean operations

"==", "!=": Check for equality or inequality

"<", "<=", ">", ">=": Less than, etc

<pre class="prettyprint" data-lang="python">
# examples
participant_answer == correct_answer
84/12 > 10
current_trial_num != 1 and current_trial_num < 10
current_trial_num < 10 or current_trial_num > 50
</pre>


---
title: Basic syntax
subtitle: if, else statements

Perform operations based on a condition

<pre class="prettyprint" data-lang="python">
a = 8
b = 7
correct_answer = a + b
question = "What is {} + {}?".format(a,b)
participant_answer = int(input(question))
if participant_answer == correct_answer:
	print("Correct!")
else:
	print("Incorrect")
</pre>

<p class="output">
What is 8 + 7?: 15 <br>
Correct!
</p>

---
title: Basic syntax
subtitle: if, else statements: Psychology example

Use elif to check more than two outcomes

<pre class="prettyprint" data-lang="python">

if trial_type == "Practice":
	stim = Stimulus("These trials are just for practice")
elif trial_type == "Pre-test":
	stim = Stimulus("You will now begin the real task")
elif trial_type == "Manipulation":
	stim = Stimulus("You will now perform a different task")
elif trial_type == "Post-test":
	stim = Stimulus("You will now begin the final task")
show_on_screen(stim)

</pre>

---
title: Basic syntax
subtitle: while loops

Perform an action until a condition is met

<pre class="prettyprint" data-lang="python">
handedness = ""
while handedness != "L" or handedness != "R":
	handedness = input("Enter your preferred hand (L or R)")
print("Thanks!")
</pre>

<p class="output">
Enter your preferred hand (L or R) T<br>
Enter your preferred hand (L or R) g<br>
Enter your preferred hand (L or R) R<br>
Thanks!
</p>

Use "while True" to run indefinitely, until "break"

---
title: Basic syntax
subtitle: Defining functions

Re-use your code without duplicating

<pre class="prettyprint" data-lang="python">
# define function "shout" that prints text with "!"
def shout(text, loudness=1):
	print( text + "!" * loudness )

shout("Hi")
shout("Hello", loudness=5)
shout("Goodbye")
</pre>

<p class="output">
Hi!<br>
Hello!!!!!<br>
Goodbye!
</p>

Functions can return values, e.g. len(x) returns length of x

---
title: Basic syntax
subtitle: Defining functions: Psychology example

<pre class="prettyprint" data-lang="python">
def check_if_clicked(stimuli):
	distance = stimuli.position - cursor.position
	if distance < 100: # e.g. less than 100 pixels
		clicked = True
	else:
		clicked = False
	return clicked

clicked_stim_1 = check_if_clicked(stimuli1)
clicked_stim_2 = check_if_clicked(stimuli2)
# now we know which one was clicked...
</pre>


---
title: Packages and Modules
subtitle: Importing modules

<pre class="prettyprint" data-lang="python">
import random
# 0-1
print(random.random())
# random choice (e.g. counterbalance between subjects)
options = ["preferred", "non-preferred"]
chosen_option = random.choice(options)
print(chosen_option)
# randomising a list (e.g. randomising trial order)
colour_list = ["red","green","blue"]
random.shuffle(colour_list)
print(colour_list)
</pre>

<p class="output">
0.2803702968196148<br>
Please use your preferred hand<br>
['blue', 'red', 'green']
</p>


---
title: Packages and Modules
build_lists: True

To install a package you will use "pip"

- If you downloaded WinPython, find your install directory and launch WinPython Command Prompt
	- Type "pip install packagename"
- Anaconda- not sure
- Then will be available using "import packagename" in your script


---
title: Packages and Modules
build_lists: True

Other useful modules

- Pandas - R-like dataframes and functions (<a href="https://github.com/pandas-dev/pandas/blob/master/doc/cheatsheet/Pandas_Cheat_Sheet.pdf">info</a>)
- MatPlotLib - Plotting like MATLAB
- Seaborn - statistical data visualization
- numpy - Complex maths operations, MATLAB like
- SciPy - Scientific package (including stats)


---
title: Resources

Learn by trying it out, not reading

- <a href="https://repl.it/languages/python3">repl.it - Play with code in your web browser</a>
- <a href="https://www.tutorialspoint.com/python/python_quick_guide.htm">Starter tutorial</a>
- <a href="https://www.codecademy.com/learn/python">Codecademy course</a>
- <a href="https://www.python.org/dev/peps/pep-0008/">Python style guide</a>
- <a href="https://en.wikipedia.org/wiki/Python_syntax_and_semantics">Python syntax (Wiki)</a>
- <a href="https://reddit.com/r/learnpython">/r/learnpython</a>



---
title: General tips
subtitle: Problem solving
build_lists: True

- Expect problems
- Your problem is rarely unique
- Google effectively
	- bad: "change one thing to another in a list of strings"
	- good: "replace element in list python"
- Hone in on the problem
	- See if you can replicate it in a new script