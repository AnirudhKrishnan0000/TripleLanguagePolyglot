# Triple Language Polyglot
A polyglot that can be run in 3 different languages (Python, Lua, JS)

## Example for polyglot
This example polyglot prints which language it is running in:
```
a=1;
--a//(lambda: eval("print('Python')") or exit(0))()
--a; lambda: eval("console.log('JavaScript')"); process.exit(0)

print("Lua")
```

## How it works
The polyglot has this line:
```
a=1;
```
This line is syntactically correct in all 3 languages.

The next line of the polyglot:
```
--a//(lambda: eval("print('Python')") or exit(0)()
```
It is commented out in Lua by the --a at the start, and commented out in JS as well with the //.

It is a lambda expression for Python.

Now after that line:
```
--a; lambda: eval("console.log('JavaScript')"); process.exit(0)
```
It is a Python lambda expression and JavaScript label that is commented out in Lua by the --a.

After all these lines, it can be just pure Lua, because of the exit and process.exit that caused Python and JS to end the program early, they do not interpret the Lua code.

## How to construct your own polyglot
### First step: Make a project folder
It is recommended to make a project folder with 3 files.
The three files you should create are:

• A Lua file (.lua)

• A Python file (.py)

• A JavaScript file (.js)

• A final polyglot file (any file extension)



Now place all the payloads you need to execute in these three files.



### Second step: Compress your Python and JS code into 1 line
The reason why you have to compress the Python and JS code into 1 line is because you have to fit it in the eval. Lua code is fine and does not have to be compressed.
The way you do this in both languages is you replace newlines with literal "\n" text inside the file.

### Third step: Construct the polyglot with all your code
To construct the polyglot, you have to now paste your code into the template:
```
a=1;
--a//(lambda: eval("YOUR PYTHON SOURCE HERE") or exit(0))()
--a; lambda: eval("YOUR JAVASCRIPT SOURCE HERE; process.exit(0)")()
a=1//((not hasattr)and load("YOUR LUA SOURCE HERE")())
```
Place your final code into the polyglot file.

### Fourth step: Test the polyglot
To test the polyglot, you have to call all 3 interpreters on the polyglot file.
Type these commands in the terminal:
```
python3 my_project_folder/polyglot
lua my_project_folder/polyglot
node my_project_folder/polyglot
```
They should execute the provided source code you placed in the polyglot.
