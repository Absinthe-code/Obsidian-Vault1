everything is an object

an object has attributes (red,yellow,big)

an object has functions or METHODS in the context of an object

has 2 types of numbers int for integers and floats for number with decimal point

- type(): gets the type of an object

5/5 = 1.0

5//5 = 1

** to use exponents

% gets the modulus 

BIDMAS is the order of operations

if i have a variable it is stored in memory like age = 25 i can call it anywhere

age += 5 is gonna reassign the age to age +5
age -= 5 is gonna reassign the age to age -5
age /= 2 divides it by two ecc ecc

strings are just a sequence of characters

single quotes or double quotes is the same

pay attention to apostrophes

\\ is the escape character

python indexes from 0 

a string is just an array, you can call stringName\[1] to call the second character of the string

stringName\[-3] to start from the end

stringName\[0:3] to slice a string to get the first 3 characters. 
	startpoint is inclusive
	endpoint is not inclusive
	
string concatenation can be done with + strings can be repeated by using * and a number

### string methods

string.upper() makes it uppercase

string.split(',')  splits the string every , character

string.length?

len(string) gives the length

format method
	print("num1 is {0} and num2 is {1}".format(num1,num2))
	everything after the .format is indexed and you call by index in the parenthesis
	 you can have options for the format method adding : after the index
	 {0:.3}  in this case .3 is saying take the first 3 digits, not the decimal points
	 {0:.3f} is saying floating, meaning the precision after the dot

f-strings 
	print(f"num1 is {num1} and num2 is {num2:.4f}")
	add f in front of the string and you can call the variable name
	formatting works the same way
### lists (arrays)

string.split gives you a list

a list is an array

you declare them with square brackets

list = \["bro",1 ,"spam",true]

list\[1] gives you the second item

also works with -

also works like strings like list\[0:2]

you can concatenate with +

can change items in a list like
	list\[0] = "bruh"

list.append() adds the value at the end of the list

list.pop eliminates the last one

list.remove(value you want to remove)
	it removes the first instance of it

del(list\[5]) removes the element at index 5

you can have lists within a list which is basically a matrix

list = \[\[1,2,3],\[4 5 6]]

indexing a matrix returns a list

list\[0] = \[1,2,3]

list\[0]\[1] = \[2]

\# is comments

int() to typecast from something to an integer

### Logic

if wants a colon : 

elif is else if

### Functions

def to define functions

def doStuff()
	print("stuff is done")

















