# Features

## Keywords

*** Declaration***

- var
- const
- function
- thematic
- statement

*** Classes ***

- class
- new
- this
- super
- extends
- static

*** Error Handling ***

// not implemented

- try
- catch
- finally
- throw

*** Control Flow ***

- if
- else
- for
- while
- do
- never
- switch
- case
- default
- break
- continue
- return
- when

*** Import & Export ***

- import
- export
- from

*** Special Control Flow ***

- del
- unpack
- watch
- defer

*** Unary Operators ***

- typeof
- copyof
- not
- memoize
- dememoize
- identity

*** Binary Operators ***

- in
- not in
- as
- of
- and
- or
- nand
- nor
- xor
- not instanceOf
- instanceOf
- is
- is not

## Identifiers

*** Description ***
- Identifier must start with a letter, underscore or dollar sign.
- Identifier can contain letters, digits, underscores, and dollar signs.
- Identifier cannot contain spaces or special characters.
- Identifier cannot be a reserved keyword.

*** Examples ***
- hypermatrix
- hypermatrix1
- hypermatrix_1
- hypermatrix$1
- _hypermatrix_1$
- $hypermatrix_1$2
- $_hypermatrix_12

*** Reserved Identifiers ***

// This indicates that reserved identifiers are used by the language itself
// and cannot be used as variable or function names, except when used
// as property names in object member expressions.

- true
- false
- null
- undefined
- NaN
- Infinity
- _Infinity
- this
- super

// These identifiers are not currently reserved but using them may lead to issues

*** Row Identifiers ***

// Row identifiers allow referencing functions or members by their exact signature.
// Useful for precise function overloading or interfacing.

// Example:
// #["sum(int, int)"]
// #["join(string, string)"]

``` hypermatrix

~~~~~~~~~~ Put to other variable ~~~~~~~~

var SUM = #["sum(int, int)"];


~~~~~~~~~ Show how to use ~~~~~~~~

println(SUM(1, 2)); // Output: 3

println(sum(1, 2) === SUM(1, 2)); // Output: true


~~~~~~~~~~~~ Definition ~~~~~~~~

function sum(int a, int b) {
    return a + b;
}

```

## Comments

*** Single-line Comments ***
// This is a single-line comment.

*** Multi-line Comments ***
/*
This is a multi-line comment.
It can span multiple lines.
*/

*** Documentation Comments ***
/**
 * This is a documentation comment.
 * It can be used to document functions, classes, and other constructs.
 */

*** Section Comments ***

// Section comments are used to group related code sections for better organization.
// They must be visually distinct in IDEs to enhance readability.
//
// Format rules:
// 1. Start with at least three tildes: ~~~
// 2. Can optionally start with pipe: |~~~
// 3. Must end with at least three tildes: ~~~
// 4. Can optionally end with pipe: ~~~|
//
// Examples:
// ~~~ Section Name ~~~
// |~~~ Section Name ~~~
// ~~~ Section Name ~~~|
// |~~~ Section Name ~~~|
//
// You can write code after a pipe-ended section:
// ~~~~~~~ Print ~~~~~~~| println("Hello, World!"); // This will print "Hello, World!"

> in language example:
``` hypermatrix

~~~ Declaration ~~~
var a, b, c;

~~~~~~~~ Assignment ~~~~~~~~
a = 1;
b = 2;
c = a + b;

~~~~~~~~~ Print ~~~~~~~~| println(c);

|~~~ End ~~~|

```


## Literals

*** String Literals ***
"This is a string literal."

*** Int Literals ***
123

*** Float Literals ***
123.45

*** Boolean Literals ***
true
false

*** Array Literals ***
[1, 2, 3]

*** Tuple Literals ***
(1, 2, 3)

*** Set Literals ***
<1, 2, 3>

*** Matrix Literals ***
M[1, 2, 3]
|[4, 5, 6]
|[7, 8, 9]

*** Object Literals ***
{name: "John", age: 30}

## Patterns

*** Object Pattern ***

``` hypermatrix

const person = {name: "John", age: 30, weight: 70, height: 175, gender: "male"};

const {name, age} = person;
// name = "John"
// age = 30

const {PName: name, PAge: age} = person;

// PName = "John"
// PAge = 30

const {weight = 72, height = 180, bmi = 25} = person;
// weight = 70
// height = 175
// bmi = 25

```

*** Array Pattern ***

``` hypermatrix

const arr = [1, 2, 3, 4, 5];

const [a, b, c] = arr;
// a = 1
// b = 2
// c = 3

del a, b, c;

const [a, b, c, d = 41, e = 51] = [11, 22, 33, 44];
// a = 11
// b = 22
// c = 33
// d = 44
// e = 51

del a, b, c, d, e;

const [a, b] = (1, 2);
// a = 1
// b = 2

```

*** Tuple Pattern ***

``` hypermatrix

const (a, b, c) = true;
// a = true
// b = true
// c = true

del a, b, c;

const (a, b, c) = (1, 2, 3);
// a = (1, 2, 3)
// b = (1, 2, 3)
// c = (1, 2, 3)

del a, b, c;

const (a, b) = [1, 2, 3];
// a = [1, 2, 3]
// b = [1, 2, 3]

del a, b;

const a = (1, 2, 3);
// a = (1, 2, 3)

```

*** Params Pattern ***

// is only used in function, statement and... params
``` hypermatrix
function sum(a, b) {
    return a + b;
}

function sum(a: int, b: int) {
    return a + b;
}

function sum(a: int = 1, b: int = 2) {
    return a + b;
}

function sum(int a, int b) {
    return a + b;
}

function sum(int a = 1, int b = 2) {
    return a + b;
}

```

## Unit

// 1m
// 100cm

``` hypermatrix

const float km = 1000;
const float m = 1;
const float cm = 0.01;
const string unit = "cm";

println(100cm == 1m); // true

println(1000m == 1km); // true
println(1000m == 1.1km); // false
println(1100m == 1.1km); // true

println(1.5km); // 1500
println(2cm); // 0.02

println(5unit); // "cmcmcmcmcm"

// Units are shorthand for multiplying a number by a unit value (e.g. 1m = m * 1)

```

*** Unit ***

## Error Handling

// Error handling is in its early stages and currently supports basic Syntax and Runtime Errors.
// Future updates will include custom exceptions and error propagation mechanisms.
// Apologies for the current limitations - this is a work in progress being shared with the community
// Error handling capabilities will be enhanced in future releases

// Error handling is currently limited to basic Syntax Errors and Runtime Errors
// Unhandled errors may propagate from the parent language
// More comprehensive error handling will be added in future versions

// Example:
``` hypermatrix

try {
    var result = 10 / 0;
} catch (e) {
    println("Error: " + e.message);
} finally {
    println("End of error handling.");
}

throw "This is a runtime error";
throw new Error("This is a custom error");

```

## Watchers (experimental)

// Watchers are an experimental feature used to observe and react to changes in values
// They allow executing code when specific mutations or updates occur to watched variables
// Currently supports watching variables, arrays, and object properties
// Future versions will add more granular watching capabilities and performance optimizations

// Example:
``` hypermatrix

watch arr.pop() {
    println("remove -> " + this);
}

watch arr.push() {
    println("push -> " + this);
}

watch arr {
    println("changed to -> " + this);
}

var arr = [1, 2, 3, 4, 5];

arr.push(6); // its call the second watcher and print "add -> 6"

arr.pop(); // its call the first watcher and print "remove -> 6"

arr = [1, 2, 3, 4, 5]; // its call the third watcher and print "changed to -> [1, 2, 3, 4, 5]"

```

## Defers

// Defers are a feature that allows you to schedule code execution for later,
// even after the current function has returned.
// They are useful for tasks that need to be executed after the current function has finished,
// such as cleanup operations or resource management.

> Note: Defers have access to all variables in the current scope because they are executed in the end of scope.

// Example:
``` hypermatrix

defer {
    println("defer");
};

defer (1000) {
    println("program defer");
};

println("Program");


if (true)  {
    defer (2000) {
        println("block defer");
    };

    println("Block");
}

println(sum(5, 6));

function sum(a, b) {
    defer (1000) {
        println("the sum = " + sum);
    };

    number sum = a + b;
    return sum;
}

~~~~~~~~~~~ Result ~~~~~~~~~~~|/*

Program
Block
block defer
the sum = 11
11
defer
program defer

*/

```

## Unpack (in progress)

// Unpack is a feature that allows you to extract values from an array or object and assign them to variables.
// It provides a convenient way to work with arrays and objects in a more readable and concise manner.

// Example:
``` hypermatrix

// the system is built-in object
unpack (system) {
    println(screenWidth);
    println(screenHidth);

    keyPrint("windows", "tab");
}

var arr = [1, 2, 3, 4, 5];

unpack(arr) {
    println(_0_); // 1
    println(_2_); // 3
    println(_4_); // 5
}

```

## Build-in

### *** Objects ***

### System Object

#### System.setTimeout(callback, delay)
Sets a timer which executes a function once the timer expires.

#### System.setInterval(callback, delay)
Repeatedly calls a function with a fixed time delay between each call.

#### System.setDoInterval(callback, delay)
Similar to setInterval but executes callback immediately before starting interval.

#### System.nextFrame(callback)
Executes a function on the next animation frame.

#### System.sleep(milliseconds)
Pauses execution for specified milliseconds.

#### System.startTimer()
Starts recording elapsed time.

#### System.stopTimer()
Stops recording elapsed time.

#### System.now()
Returns current timestamp.

#### System.setClipBoard(text)
Sets system clipboard text.

#### System.getClipBoard()
Gets system clipboard text.

#### System.beep()
Plays system beep sound.

#### System.wait()
Waits for user input.

#### System.exit()
Exits the program.

#### System.monitorWidth
Returns primary monitor width.

#### System.monitorHeight
Returns primary monitor height.

#### System.monitorRate
Returns monitor refresh rate.

#### System.screenWidth
Returns screen width.

#### System.screenHeight
Returns screen height.

#### System.screenResolution
Returns screen resolution.

#### System.getDesktopProperty(propertyName)
Gets system desktop property value.

#### System.pixelColor(x, y)
Gets pixel color at specified coordinates.

#### System.mouseLocation()
Gets current mouse position.

#### System.mouseMove(x, y)
Moves mouse cursor to specified coordinates.

#### System.mouseClick()
Simulates mouse click.

#### System.mouseClickAt(x, y)
Simulates mouse click at specified coordinates.

#### System.mouseDoubleClickAt(x, y)
Simulates mouse double click at specified coordinates.

#### System.mouseWheel(amount)
Simulates mouse wheel scroll.

#### System.mousePress(...buttons)
Simulates mouse press.

#### System.mouseRelease(...buttons)
Simulates mouse release.

#### System.keyPress(...keys)
Simulates key press.

#### System.keyRelease(...keys)
Simulates key release.

#### System.keyType(...keys)
Simulates key type.

#### System.keyPrint(...keys)
Simulates pressing multiple keys simultaneously, then releases them all.

#### Future Enchantments
// more functions is coming soon

### Terminal Object

#### Terminal.print(...any)
Prints text without a newline.

#### Terminal.println(...any)
Prints text with a newline.

#### Terminal.input(before, after)
Gets user input from terminal.

#### Terminal.readHidden(before, after)
Gets hidden user input from terminal.

#### Terminal.clear()
Clears the terminal screen.

#### Terminal.pause(repeatPause)
Pauses terminal execution.

#### Terminal.ignore(numberOfChars)
Ignores terminal input.

#### Terminal.args
Gets command line arguments.

#### Future Enchantments
// Terminal Color and Font Style Support
// Features:
// - Set text colors (foreground/background)
// - Apply font styles (bold, italic, underline)
// - Support for text markers/anchors
// - Ability to manipulate text between markers
// - Real-time text modification and deletion

### *** Functions ***

### Print Functions
// Prints any value to the console without a newline
// print(...values)

### Println Functions
// Prints any value to the console with a newline
// println(...values)

### Input Functions
// Gets user input from terminal
// input(before, after)

### Eval Functions
// Evaluates a string as HyperMatrix code
// eval(code)

### *** Classes ***

### Math Class

#### Math Constants

Math.HPI = 1.570796326794897
Math.PI = 3.141592653589794
Math.TAU = 6.283185307179588
Math.E = 2.718281828459045

#### Math.abs(x)
Returns the absolute value of a number.

#### Math.acos(x)
Returns the arccosine of a number.

#### Math.asin(x)
Returns the arcsine of a number.

#### Math.atan(x)
Returns the arctangent of a number.

#### Math.atan2(y, x)
Returns the arctangent of the quotient of its arguments.

#### Math.ceil(x)
Returns the smallest integer greater than or equal to a number.

#### Math.clamp(value, min, max)
Returns value clamped between min and max.

#### Math.cos(x)
Returns the cosine of a number.

#### Math.cosh(x)
Returns the hyperbolic cosine of a number.

#### Math.exp(x)
Returns e raised to the power of a number.

#### Math.floor(x)
Returns the largest integer less than or equal to a number.

#### Math.hypot(x, y)
Returns the square root of the sum of squares of its arguments.

#### Math.int(x)
Returns the integer value of a number.

#### Math.log(x)
Returns the natural logarithm of a number.

#### Math.log10(x)
Returns the base 10 logarithm of a number.

#### Math.max(...values)
Returns the largest of zero or more numbers.

#### Math.min(...values)
Returns the smallest of zero or more numbers.

#### Math.onOff()
Returns random 1 or 0 number.

#### Math.pow(x, y)
Returns base to the exponent power.

#### Math.random()
Returns a pseudo-random number between 0 and 1.

#### Math.round(x)
Returns the value of a number rounded to the nearest integer.

#### Math.sign(x)
Returns the sign of the x, indicating whether x is positive, negative or zero.

#### Math.sin(x)
Returns the sine of a number.

#### Math.sinh(x)
Returns the hyperbolic sine of a number.

#### Math.sqrt(x)
Returns the positive square root of a number.

#### Math.tan(x)
Returns the tangent of a number.

#### Math.tanh(x)
Returns the hyperbolic tangent of a number.

#### Math.toDegrees(x)
Converts radians to degrees.

#### Math.toPoint(x, y)
Creates a point from x,y coordinates.

#### Math.toRadians(x)
Converts degrees to radians.# Expressions

#### Future Enhancements
- Additional mathematical operations
- 2D rendering and point manipulation
- Vector and matrix operations
- Geometric transformations
- Advanced trigonometric functions
- Statistical calculations
- Complex number support // no sure if this is needed

// Note: some functions may be added to specialized classes like Math2D, Matrix2D, or Vector2D instead of Math

### TerminalMatrix Class (Terminal Ascii Canvas)
// coming soon...

### Date Class
// Coming soon...

### Interval Class
// i need some ideas for this
// may it come in the future

### Matrix Class (Window)
// Work in progress
// The name is temporary

### Json Class
// Coming soon...

### File Class
// Coming soon...

### Console Class
// Coming soon...

### OS Class
// Coming soon...

### Matrix2D Class
// Coming soon...

### Matrix3D Class
// not sure if this is needed but it would be nice to have

# Expressions

## Type Expressions

### Any (Default)

<any> = undefined
<any> = null
<any> = 1
<any> = 1.0
<any> = "string"
<any> = F"string: #{value}"
<any> = true
<any> = false
<any> = [1, 2, 3]
<any> = ["hello", "world"]
<any> = <%AnyOtherType%>

### Auto (Detctect Value Type)

<any> >>> <auto> = 1 -> auto change to int
<any> >>> <auto> = 1.0 -> auto change to float
<any> >>> <auto> = "hello" -> auto change to string

### Null (None-Type)

<any> >>> <null> = null

### Undefined (None-Type)

<any> >>> <undefined> = undefined

### Number Type

<any> >>> <number> >>> <float> = 1.0
<any> >>> <number> >>> <float> >>> <int> = 1
<any> >>> <number> >>> <float> >>> <NaN> = NaN
<any> >>> <number> >>> <float> >>> <Infinity> = Infinity
<any> >>> <number> >>> <float> >>> <_Infinity> = _Infinity

### String Type

<any> >>> <string> = "hello"
<any> >>> <string> = "Hello"
<any> >>> <string> = "2025"
<any> >>> <string> = ""

### Boolean Type

<any> >>> <boolean> = true
<any> >>> <boolean> = false

### Array Type

<any> >>> <array> = [1, 2, 3]
<any> >>> <array> = ["hello", "world"]
<any> >>> <array> = [1, "hello", true]
<any> >>> <array> = [1, "hello", true, [1, 2, 3]]
<any> >>> <array> = [1, "hello", true, [1, 2, 3], {a: 1, b: 2}]

### Tuple Type

<any> >>> <tuple> = (1, 2)
<any> >>> <tuple> = (1, 2, 3)
<any> >>> <tuple> = (1, 2, [1, 2, 3], {a: 1, b: 2})
<any> >>> <tuple> = (1, 2, println, system)

### Set Type
<any> >>> <set> = <1>
<any> >>> <set> = <1, 2>
<any> >>> <set> = <1, 2, 3>
<any> >>> <set> = <1, (a, b), [1, 2, 3], {a: 1, b: 2}>

### Matrix Type

<any> >>> <matrix> = M[1, 2, 3] -> row: 1, column: 3, length: 9
<any> >>> <matrix> = M[1, 2, 3]
                     |[4, 5, 6]
                     |[7, 8, 9] -> row: 3, column: 3, length: 9
<any> >>> <matrix> = M[1]
                     |[4, 5]
                     |[7, 8, 9] -> row: 3, column: 3, length: 9
<any> >>> <matrix> = M[0, 1, 1, 0, 1, 0, 1, 1, 0]
                     |[0, 1, 1, 0, 1, 0, 1, 1, 0]
                     |[1, 0, 1, 1, 0, 1, 0, 1, 1]
                     |[1, 1, 0, 0, 1, 1, 1, 1, 0]
                     |[0, 1, 1, 0, 1, 0, 1, 1, 0]
                     |[0, 1, 1, 0, 1, 0, 1, 1, 0]
                     |[1, 0, 1, 1, 1, 1, 0, 0, 1]
                     |[1, 0, 1, 1, 0, 1, 0, 1, 1]
                     |[1, 1, 0, 0, 1, 1, 1, 1, 0] -> row: 9, column: 9, length: 81
<any> >>> <matrix> = M[]
                     |[5]
                     |[7, 8, 9] -> row: 3, column: 3, length: 9 => save like this M[null, null, null]
                                                                                  |[5, null, null]
                                                                                  |[7, 8, 9]

### Object Type

<any> >>> <object> = {a: 1, b: 2}
<any> >>> <object> = {a: 1, b: 2, c: {a: 1, b: 2}}
<any> >>> <object> = {a: 1, b: 2, c: {a: 1, b: 2}, d: [1, 2, 3]}
<any> >>> <object> = {a, b, c: {a, b}, d: [1, 2, 3]}

### Function Type

<any> >>> <Function> >>> => {
    function sum(a, b) {
        return a + b;
    }
}
<any> >>> <Function> >>> => {
    function sum(a: int, b: int): int {
        return a + b;
    }
}
<any> >>> <Function> >>> => {
    int sum(a: int, b: int) {
        return a + b;
    }
}
<any> >>> <Function> >>> => {
    int sum(int a, int b) {
        return a + b;
    }
}

### AnonymousFunction Type

<any> >>> <Function> >>> <AnonymousFunction> = function() {}
<any> >>> <Function> >>> <AnonymousFunction> = function(a, b) {}
<any> >>> <Function> >>> <AnonymousFunction> = a -> {}
<any> >>> <Function> >>> <AnonymousFunction> = (a, b) -> {}

### ThematicName Type

<any> >>> <Thematic> => {
    thematic fullname {
        return "Hyper" + "Matrix";
    } value {
        println(value);
    }
}
<any> >>> <Thematic> => {
    thematic fullname: string {
        return "Hyper" + "Matrix";
    } value: string {
        println(value);
    }
}
<any> >>> <Thematic> => {
    thematic string fullname {
        return "Hyper" + "Matrix";
    } value: string {
        println(value);
    }
}
<any> >>> <Thematic> => {
    thematic fullname {
        return "Hyper" + "Matrix";
    } string value {
        println(value);
    }
}

### AnonymousThematic Type

<any> >>> <Thematic> >>> <AnonymousThematic> =  thematic {
                                                    return "Hyper" + "Matrix";
                                                } value {
                                                    println(value);
                                                }
<any> >>> <Thematic> >>> <AnonymousThematic> =  thematic: string {
                                                    return "Hyper" + "Matrix";
                                                } value {
                                                    println(value);
                                                }
<any> >>> <Thematic> >>> <AnonymousThematic> =  thematic: string {
                                                    return "Hyper" + "Matrix";
                                                } value: string {
                                                    println(value);
                                                }
<any> >>> <Thematic> >>> <AnonymousThematic> =  thematic: string {
                                                    return "Hyper" + "Matrix";
                                                } string value {
                                                    println(value);
                                                }

### Statement Type

<any> >>> <Statement> => {
    // Joke If :D => somtimes it's true, sometimes it's false by given chance
    statement If: block {
        ~> (int chance = 50) {
            block() when true.flip(chance) else this.Else();
        } Else {
            block();
        }
    }
}
<any> >>> <Statement> => {
    // loop statement with index applyed to 'this' like 'this.index'
    statement loop: block {
        ~> (int times = 10, int index = 0, update = 1) {
            for (int i = index; i < times; i += update) {
                block({index: i});
            }
        }
    }
}
<any> >>> <Statement> => {
    statement IfPostive: blk {
        ~> (n) {
            if (n > 0)
                blk({num: n});
            else this.isZero(n)

        } isZero(n) {
            if (n == 0)
                blk({num: n});
            else this.isNegative(n)

        } isNegative(n) {
            if (n < 0)
                blk({num: n});
        }
    }
}


### AnonymousStatement Type

<any> >>> <Statement> >>> <AnonymousStatement> = statement: block {
                                                    ~> (int chance = 50) {
                                                        block() when true.flip(chance) else this.Else();
                                                    } Else {
                                                        block();
                                                    }
                                                }
<any> >>> <Statement> >>> <AnonymousStatement> = statement: block {
                                                    ~> (int times = 10, int index = 0, update = 1) {
                                                        for (int i = index; i < times; i += update) {
                                                            block({index: i});
                                                        }
                                                    }
                                                }
<any> >>> <Statement> >>> <AnonymousStatement> = statement: blk {
                                                    ~> (n) {
                                                        if (n > 0)
                                                            blk({num: n});
                                                        else this.isZero(n)

                                                    } isZero(n) {
                                                        if (n == 0)
                                                            blk({num: n});
                                                        else this.isNegative(n)

                                                    } isNegative(n) {
                                                        if (n < 0)
                                                            blk({num: n});
                                                    }
                                                }



### Class Type

<any> >>> <Class> = <ClassDeclaration>

### AnonymousClass Type

<any> >>> <Class> >>> <AnonymousClass> = // ASAP :D

### Instance Type

<any> >>> <Instance> >>> <?> = <ClassConstruction>

### Block Type

// ~~~~~~~~~~ Normal Block ~~~~~~~~~~
{
    println("Hello World");
}

// ~~~~~~~~~~ Single Line Block ~~~~~~~~~~
    println("Hello World");

// ~~~~~~~~~~ Empty Block ~~~~~~~~~~
'{}' or ';'

### Native Type

#### NativeFunction Type

<any> >>> <Function> >>> <NativeFunction> = <NativeDeclaration>

#### NativeThematic Type

<any> >>> <Thematic> >>> <NativeThematic> = <NativeDeclaration>

#### NativeStatement Type

<any> >>> <Statement> >>> <NativeStatement> = <NativeDeclaration>



## Number Expressions

### Number Binary Operators

5 + 5 = 10
5 - 5 = 0
5 * 5 = 25
5 / 5 = 1
7 % 5 = 2
5 ** 5 = 3125

5 + 5 * 5 = 30 -> 5 + (5 * 5)
(5 + 5) * 5 = 50


### Number Unary Operators

+4 = 4      -> Positive
-4 = -4     -> Negative
++4 = 5     -> Increment
--4 = 3     -> Decrement
%%4 = 16    -> Squrement


### Number Prefix Operators

4++ = 4 -> Post Increment after 5
4-- = 4 -> Post Decrement after 3
4%% = 4 -> Post Squrement after 16

### Number Comparison Operators

5 > 4 = true
5 < 4 = false
4 >= 4 = true
5 <= 4 = false
5 == 5 = true
5 != 5 = false
5 == "5" = true
5 != "5" = false
5 === 5 = true
5 !== 5 = false
5 === "5" = false
5 !== "5" = true
5.1 ~= 5 = true
5.1 !~= 5 = false
5.1 ~= "5" = true
5.1 !~= "5" = false
5.1 ~= 5.0 = true
5.1 !~= 5.0 = false
5.1 ~= "5.0" = false
5.1 !~= "5.0" = true
5 in 50 = true
5 in 1.05 = true
52 in 50 = false
52 in 1.05 = false
5 not in 50 = false
5 not in 1.05 = false
52 not in 50 = true
52 not in 1.05 = true

## String Expressions

### String Binary Operators

"Hyper" + "Matrix" = "HyperMatrix"
"Matrix" + " " + "Grammer" = "Matrix Grammer"
"HyperMatrix" - "r" = "HypeMatix"
"Hello, World" * "o"  "HellO, WOrld"
"Hello, World" / "o"  "Hello_, Wo_rld"
"Hello, World" % "o"  "Hell , W rld"
"Hello, World" ** "o"  "Hell O, W Orld" -> "bobisgoodbobisslow" ** "bob" = " BOBisgood BOBisslow"

"HyperMatrix" + 3 = "HyperMatrix3"
"HyperMatrix" - 3 = "HyperMat"
"Hyper" * 5 = "HyperHyperHyperHyperHyper"
"Matrix" ** 5 = "Matrix
Matrix
Matrix
Matrix
Matrix"
"Hyper" * -5 = "repyHrepyHrepyHrepyHrepyH"
"HyperMatrix" / 3 = "Hyp"
"HyperMatrix" % 3 = "erMatrix"
"Matrix" ** -5 = "xirtaM
xirtaM
xirtaM
xirtaM
xirtaM"

### String Comparison Operators

"hello" == "hello" = true
"5.236" == 5.236 = true
"hello" != "hello" = false
"5.236" != 5.236 = false
"hello" === "hello" = true
"5.236" === 5.236 = false
"hello" !== "hello" = false
"5.236" !== 5.236 = true
"HeLlo" ~= "hello" = true
"HeLlo" !~= "hello" = false
"HeLlo" ~= "Hello" = true
"HeLlo" !~= "Hello" = false
"HeLlo" ~= "Hello" = true
"hello" > 5 = false
"hello" < 5 = false
"hello" >= 5 = true
"hello" <= 5 = true
"ab" > "aa" = true
"aa" < "ab" = true
"aa" >= "ab" = false
"ab" <= "aa" = false
"aa" > "aa" = false
"aa" < "aa" = false
"aa" >= "aa" = true
"aa" <= "aa" = true
"hello" in "hello, world" = true
"hello" not in "hello, world" = false

## Boolean Expressions

### Boolean Binary Operators

true + true = true
true + false = true
true - true = true
true - false = false
5 + true = 6
5 - true = 4
5 + false = 5
5 - false = 5
5 * true = 5
5 * false = 0


### Boolean Comparison Operators

true == true = true
true == false = false
true != true = false
true != false = true
true === true = true
true === false = false
true !== true = false
true !== false = true
true == "true" = true
true == "false" = false
true != "true" = false
true != "false" = true
true === "true" = false
true === "false" = false
true !== "true" = true
true !== "false" = true
true ~= true = true
true ~= false = false
true !~= true = false
true !~= false = true
true ~= "true" = true
true !~= "true" = false
true > false = true
false < true = true
false >= true = false
true <= false = false
true >= true = true
false <= false = true

## Solid Operators

### Solid Binary Operators

null ?? "hello" = "hello"
"ok" ?? "hello" = "ok"
undefined ?? "hello" = "hello"
"ok" ?? "hello" = "ok"
null ?? undefined = undefined
undefined ?? null = null

"array: " + [1, 2, 3] = "array: [1, 2, 3]"
[1, 2, 3] + " <- array" = "[1, 2, 3] <- array"

true !! "hello" = "hello"
false !! "hello" = null
1 !! "hello" = "hello"
0 !! "hello" = null
"ok" !! "hello" = "hello"
"" !! "hello" = null

true || true = true
false || true = true
"ok" || "fine" = "ok"
"" || "fine" = "fine"
1 || 2 = 1
0 || 3 = 3

true && true = true
false && true = false
"ok" && "fine" = "fine"
"" && "fine" = ""
1 && 2 = 2
0 && 3 = 0

### Solid Comparison Operators

true is boolean = true
false is boolean = true
"ok" is boolean = false
"" is string = true
1 is int = true
1.0 is float = true
1 is number = false
1.0 is number = false
true is not boolean = false
false is not boolean = false
"ok" is not boolean = true
"" is not string = false
1 is not int = false
1.0 is not float = false
1 is not number = true
1.0 is not number = true

true instanceof boolean = true
false instanceof boolean = true
true instanceof any = true
"" instanceof string = true
"" instanceof any = true
1 instanceof int = true
1 instanceof float = true
1 instanceof number = true
1 instanceof any = true
1.0 instanceof int = false
1.0 instanceof float = true
1.0 instanceof number = true
1.0 instanceof any = true

true and true = true
false and true = false
false and false = false
"ok" and "fine" = true
"" and "fine" = false
"" and "" = false
1 and 2 = true
0 and 3 = false
0 and 0 = false

true or true = true
false or true = true
false or false = false
"ok" or "fine" = true
"" or "fine" = true
1 or 2 = true
0 or 3 = true
0 or 0 = false


true nand true = false
false nand true = true
false nand false = true
"ok" nand "fine" = false
"" nand "fine" = true
"" nand "" = true
1 nand 2 = false
0 nand 3 = true
0 nand 0 = true

true nor true = false
false nor true = false
false nor false = true
"ok" nor "fine" = false
"" nor "fine" = false
1 nor 2 = false
0 nor 3 = false
0 nor 0 = true

true xor true = false
false xor true = true
false xor false = false
"ok" xor "fine" = false
"" xor "fine" = true
1 xor 2 = false
0 xor 3 = true
0 xor 0 = false

### Solid Unary Operators

!true = false
!false = true
!"ok" = false
!1 = false
!0 = true

not true = false
not false = true
not "ok" = false
not 1 = false
not 0 = true

typeof true = boolean
typeof false = boolean
typeof "ok" = string
typeof 1 = int
typeof 1.0 = float

copyof true = true -> new pointer
copyof false = false -> new pointer
copyof "ok" = "ok" -> new pointer
copyof 1 = 1 -> new pointer
copyof 1.0 = 1.0 -> new pointer

identity true = {"type": "boolean", "value": true}
identity false = {"type": "boolean", "value": false}
identity "ok" = {"type": "string", "value": "ok", ascii: 218, length: 2}
identity 1 = {"type": "int", "value": 1}
identity 1.0 = {"type": "float", "value": 1.0}

memoize 5 * 5 + 5 = 30 -> save for later
5 * 5 + 5 = 30 -> return saved without calculation
memoize factorial(5) = 120 -> save for later
factorial(5) = 120 -> return saved without calculation

dememoize 5 * 5 + 5 = 30 -> with calculation and if is saved then delete it
dememoize factorial(5) = 120 -> with calculation and if is saved then delete it

## Type Definition

### Boolean

<definition> true
<definition> false

### Integer

<definition> 1
<definition> 0
<definition> -1
<definition> -9223372036854775808 // min int64
<definition> 9223372036854775807 // max int64

### Float

<definition> 1.0
<definition> 0.0
<definition> -1.0
<definition> -1.7976931348623157e+308 // min float64
<definition> 1.7976931348623157e+308 // max float64

### String

<definition> ""
<definition> "Hello World"
<definition> "Hello\nWorld"
<definition> "Hello\tWorld"
<definition> "Hello\rWorld"
<definition> "\u0126"

### FString

<definition> F""
<definition> F"Hello #{"World" * 5}" = "Hello WorldWorldWorldWorldWorld"
<definition> F"#{"Hello" * 5} #{"World" * 5}" = "HelloHelloHelloHelloHello WorldWorldWorldWorldWorld"
<definition> F"#{F"#{F"#{F"#{F"#{"Hello World"}"}"}"}"}" = "Hello World"

### Array

<definition> []
<definition> [1, 2, 3, 4, 5, 6, 7, 8, 9]
<definition> [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
<definition> ["string", true, 1, 1.5, [1, 2, 3], {"key": "value"}]

### Tuple

<definition> (1, 2)
<definition> (1, 2, 3, 4, 5, 6, 7, 8, 9)
<definition> ([1, 2, 3], [4, 5, 6], [7, 8, 9])
<definition> ("string", true, 1, 1.5, [1, 2, 3], {"key": "value"}, (1, 2, 3))

### Set

<definition> <>
<definition> <1, 2, 3>
<definition> <[1, 2, 3], [4, 5, 6], [7, 8, 9]>
<definition> <"string", true, 1, 1.5, [1, 2, 3], {"key": "value"}, (1, 2, 3), <1, 2, 3>>

### Matrix

<definition> M[]
<definition> M[1, 2, 3]
             |[4, 5, 6]
             |[7, 8, 9]
<definition> M[1, 0.5, true]
             |["Hello", false, [F"Name: #{name}", 2.5, false]]
             |[(1, true, "OK"), <0.1, 0.2, 0.5>, M[1, 2] | [3, 4]]
<definition> M[1]                M[1, null, null]
             |[2, 3]             |[2, 3, null]
             |[4, 5, 6]  same as |[4, 5, 6]

### Object

<definition> {}
<definition> {"key": "value"}
<definition> {"key": "value", key2: "value2"}
<definition> {key, "ey2: "value2", "key3": "value3"}

### Anonymous Function

<definition> () -> {}
<definition> function() {}
<definition> a -> {}
<definition> (a, b) -> {}
<definition> (a, b) -> a + b
<definition> (a, b) -> { return a + b }
<definition> function(a, b) { return a + b }
<definition> function(a) a * a

### Anonymous Thematic

<definition> thematic {
    return "hello, world!";
} value {
    println("Hello World" + value);
}
<definition> thematic: string {
    return "hello, world!";
} value {
    println("Hello World" + value);
}
<definition> thematic: string {
    return "hello, world!";
} value: string {
    println("Hello World" + value);
}
<definition> thematic: string {
    return "hello, world!";
} string value {
    println("Hello World" + value);
}

### Anonymous Statement

<definition> statement: block {
    ~> (n) {
        if (n > 0) {
            println("positive");
        } else if (n < 0) {
            this.isNegtive();
        } else {
            this.isZero();
        }
    } isZero {
        println("zero");
    } isNegative {
        println("negative");
    }
}
<definition> statement: blk {
    ~> (n) {
        if (n > 0)
            blk({num: n});
        else this.isZero(n)

    } isZero(n) {
        if (n == 0)
            blk({num: n});
        else this.isNegative(n)

    } isNegative(n) {
        if (n < 0)
            blk({num: n});
    }
}
<definition> statement: block {
    ~> (int chance = 50) {
        block() when true.flip(chance) else this.Else();
    } Else {
        block();
    }
}
<definition> statement: block {
    ~> (int times = 10, int index = 0, update = 1) {
        for (int i = index; i < times; i += update) {
            block({index: i});
        }
    }
}

## Identifier

<identifier>

ident = ""
ident52 = ""
ident_52 = ""
_ident_52_ = ""
$ident = ""
$ident$52$ = ""
$ident_52$ = ""
_$ident = ""

## Row Identifier Expression

#[<string>]

// Row identifiers allow referencing functions or members by their exact signature.
// Useful for precise function overloading or interfacing.
```hypermatrix
var newVar = #["sum(int, int)"]
```

## Member Expression

(<identifier> | <member>) . <identifier>
(<identifier> | <member>) . <call>
(<identifier> | <member>) . <member>
(<identifier> | <member>) . <memberCall>

var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];

arr.length = 9
arr.push(10);

## Call Expression

<identifier>()
<member>()

var func = () -> println("Hello World");

func();
system.wait(500);

## Assignment Expression

<identifier> = <expression>
<member> = <expression>
<pattern> = <expression>

var arr;

arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
arr.length = 5;

## As Expression

<identifier> as <identifier>
<member> as <identifier>
<call> as <identifier>

true as string = "true"
5 as string = "5"
5.0 as string = "5.0"
5.62 as int = 5
5 as float = 5.0
Math.PI as int = 3
sum(5.7, 5.3) as int = 11

const float PI = 3.14159;

int INT_PI = PI as int; // INT_PI = 3

## HashCast Expression

#<identifier> <identifier>
#<member> <identifier>
#<call> <identifier>

#boolean "" = false
#boolean " " = true
#int true = 1
#int false = 0
#int "1" = 1
#int 1.0 = 1
#int Math.OnOff() = 1 or 0
sub(5, 5) as string = "0"

## Ternary Expression

<condition> ? <expression> : <expression>
<condition> ? <truecase> : <falsecase>
<condition> ? <truecase>

1 < 2 ? 1 : 2 = 1
Math.random() > 0.5 ? "Head" : "Tail" = "Head" or "Tail"
Math.round(5.5) == 6 ? "Up" : "Down" = "Down"
Math.random(0, 100) % 2 === 0 ? "Even" : "Odd" = "Even" or "Odd"

## When Expression

<expression> when <condition> else <expression>
<truecase> when <condition> else <falsecase>
<truecase> when <condition>

5 when 1 < 2 else 10 = 5
"Head" when Math.random() > 0.5 else "Tail" = "Head" or "Tail"
"Up" when Math.round(5.5) == 6 else "Down" = "Down"
"Even" when Math.random(0, 100) % 2 === 0 else "Odd" = "Even" or "Odd"

## New Expression

new <identifier>(<expression>...)
new <class name>(<expression>...)
new <type name>(<expression>...) // ASAP :D

new Matrix(true, 50) // in progress...
new File("file.txt") // not implemented
new Date(2023, 1, 1) // coming soon...
new <type name>() // coming soon...

## Reverse Assignment Expression

<expression> => <identifier>

load("file.txt") => file

var data;
var dataStr;

Json.toObject(dataString) => data;
Json.toString(data) => dataStr;

// Json class coming soon...

## ChainPipe Expression

(<identifier> | <member> | <call>)  |> <member>
                                    |> <memberCall>
                                    |> <member>
                                    |> <memberCall>

@return <expression> // the same start point of the chain

// Example:
``` hypermatrix

var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];

println(arr); // [1, 2, 3, 4, 5, 6, 7, 8, 9]

arr
|> add(10).add(10.5)
|> add(11)
|> add(12)
|> add(13)
|> pop();
|> add(14)
|> add(15)

println(arr); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 10.5, 11, 12, 14, 15]

```

## LinePersand Expression

(<identifier> | <member> | <call>)  &> <AnonymousFunction>
                                    &> <AnonymousFunction>
                                    &> <AnonymousFunction>
                                    &> <AnonymousFunction>

@return <expression> // result of the last anonymous function

// Example:
``` hypermatrix

var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];

println(arr); // [1, 2, 3, 4, 5, 6, 7, 8, 9]

var newArr = arr
             &> nums -> nums.filter(b -> b % 2 === 0); // filter any non-even number
             &> nums -> nums.map(b -> b * 2); // double all number

println(newArr); // [4, 8, 12, 16]

var squre = arr -> arr.map(n -> n * n); // define the squre line persend or the anonymous function

const number sum = newArr
                    &> squre
                    &> #["sumOfAll(array)"];

println(sum); // 480

function sumOfAll(array arr): number {
    return arr.reduce((sum, n) -> sum + n);
}

```

# Statement

## Variable Declaration

var <identifier> = <expression>
const <identifier> = <expression>
var <identifier>: <type> = <expression>
const <identifier>: <type> = <expression>
var <pattern> = <expression>
const <pattern> = <expression>
var <pattern>: <type> = <expression>
const <pattern>: <type> = <expression>

<type> <identifier> = <expression>
const <type> <identifier> = <expression>

## Function Declaration

function <identifier>(<paramspattern>) <block>
function <identifier>(<paramspattern>): <type> <block>

<type> <identifier>(<paramspattern>) <block>

## Thematic Declaration

thematic <identifier> <getblock> <identifier> <setblock>
thematic <identifier>: <gettype> <getblock> <identifier> <setblock>
thematic <identifier>: <gettype> <getblock> <identifier>: <settype> <setblock>
thematic <gettype> <identifier> <getblock> <identifier>: <settype> <setblock>
thematic <gettype> <identifier> <getblock> <settype> <identifier> <setblock>

## Statement Declaration

statement <identifier>: <identifier> <block> {
    ~>(<paramspattern>) <block>
    <identifier>(<paramspattern>) <block>
    <identifier> <block>
    ...
}

statement <identifier>: <identifier> <block> {
    ~> <block>
    <identifier>(<paramspattern>) <block>
    <identifier> <block>
    ...
}

## Class Declaration

class <identifier> {
    <variabledeclaration>...
    <functiondeclaration>...
    <thematicdeclaration>...
    <statementdeclaration>... // soon
}

class <identifier> extends <identifier> {
    <variabledeclaration>...
    <functiondeclaration>...
    <thematicdeclaration>...
    <statementdeclaration>... // soon
}

## If Statement

if (<condition>) <block>

if (<condition>) <block>
else <block>

if (<condition>) <block>
else if (<condition>) <block>
else <block>

if (<condition>) <block>
else if (<condition>) <block>
else if (<condition>) <block>
else if (<condition>) <block>
else <block>

if <<condition>> <block>
else if (<condition>) <block>
else if (<condition>) <block>
else if (<condition>) <block>

## Switch Statement

switch (<expression>) {
    case <expression>: <inCaseBlock>
    break
    case <expression>: <inCaseBlock>
    break
    case <expression>: <inCaseBlock>
    break
    case <expression>: <inCaseBlock>
    break
    default: <inCaseBlock>
}
switch (<expression>) {
    case <expression>: <inCaseBlock>
    break
    case <expression>, <expression>: <inCaseBlock>
    break
    case <expression>, <expression>: <inCaseBlock>
    break
    case <expression>, <expression>, <expression>: <inCaseBlock>
    break
    default: <inCaseBlock>
}

switch (<expression>): <comparison> {
    case <expression>: <inCaseBlock>
    break
    case <expression>: <inCaseBlock>
    break
    case <expression>: <inCaseBlock>
    break
    case <expression>: <inCaseBlock>
    break
    default: <inCaseBlock>
}

switch (<expression>): <comparison> {
    case <expression>: <inCaseBlock>
    break
    case <expression>, <expression>: <inCaseBlock>
    break
    case <expression>, <expression>: <inCaseBlock>
    break
    case <expression>, <expression>, <expression>: <inCaseBlock>
    break
    default: <inCaseBlock>
}

switch (<expression>): <comparison> {
    case <expression> -> <block>
    case <expression>, <expression> -> <block>
    case <expression>, <expression> -> <block>
    case <expression>, <expression>, <expression> -> <block>
    default -> <block>
}

switch (<expression>): <comparison> {
    case <expression>: <block>
    case <expression>, <expression> -> <block>
    case <expression>, <expression>: <block>
    case <expression>, <expression>, <expression> -> <block>
    default: <block>
}

## For Statement

for (<initstatement>; <condition>; <updateexprsion>) <block>
for (<initstatement>; <condition>; <updatestatement>) <block>
for (<variabledeclaration> of <expression>) <block>
for (<variabledeclaration> in <expression>) <block>

## While Statement

while (<condition>) <block>

while (<condition>) <block>
never <block>

## Do While Statement

do <block> while (<condition>)

## Try Statement (not implemented)

try <block>
catch (<expression>) <block>
finally <block>

try <block>
catch (<expression>) <block>

try (<int repeat>) <block>
catch (<expression>) <block>
finally <block>

## Watch Statement (experimental)

watch <expression> <block>

## Defer Statement

defer (<expression deleyInMilis>) <block>
defer <block>

## Unpack Statement

unpack (<expression>) <block>

## Break Statement

break

break when <condition>

## Continue Statement

continue

continue when <condition>

## Return Statement

return <expression>

return when <condition> : <expression>
return when <condition> <expression>
return when <condition>; // return undefined

## Throw Statement (not implemented)

throw <expression>

throw when <condition> : <expression>
throw when <condition> <expression>
throw when <condition>; // stop program and throw defult error

## Del Statement

del <identifier>
del <identfier>, <identifier>, ...
del <member>
del <identfier>, <member>, <member>, ...
del <tuplepattern>

## Import Statement

import <string>
import from <string>
import <objectpattern> <string>
import * <string>
import <objectpattern> from <string>
import * from <string>
import <objectpattern> as <identfier> <string>
import <objectpattern> as <identfier> from <string>

## Export Statement

export <identifier>
export <declaration>
export <objectpattern>

## Block Statement

{
    <anystatement>...
}

# Archetypes

// Archetypes enable prototype-like behavior for both native and user-defined types.
// Current implementation supports basic archetype functionality.

// To inspect the archetype of a value, use the '__arche__' property -> "\_\_arche\_\_"
// User-defined archetypes are under development
// A more robust implementation will be available in future releases

# HyperMatrix Programming Language

## About the Name
HyperMatrix combines two key concepts:
- "Hyper": A high-level programming language designed for ease of use for beginners and experts alike.
- "Matrix": Specialized support for matrix-like operations and data structures with a lot of built-in functions.

> "HyperMatrix": A high-performance programming language optimized for matrix operations, applications and games.
>> Note: While current performance metrics are not finalized, future versions aim to deliver significant performance improvements.

## Development Team
Lead Developer: @DreamProgrammer

## Project Timeline
Development:
- Start Date: 2024-10-04
- Completion Date: 2024-12-11

## Release History
Version 1.0.0 (2025-01-05)
- Initial public release
- Bug fixes and stability improvements
- Function naming improvements and standardization

# Note from the Creator
Thank you for exploring the HyperMatrix programming language! This is just the beginning of what I envision as a powerful and accessible tool for developers.

Continuous Improvement: All the features described here are part of the initial release and will be improved and expanded over time. Your feedback and suggestions are invaluable in shaping the future of this language.
Join the Journey: If you’re passionate about programming languages and would like to contribute to HyperMatrix, I’d be thrilled to have you join the project. Whether it’s coding, testing, or documentation, your help is welcome!
Feel free to reach out or contribute through the project’s repository. Together, we can make HyperMatrix something truly special.

- DreamProgrammer
