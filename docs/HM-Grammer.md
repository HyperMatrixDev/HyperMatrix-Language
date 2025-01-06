# Features

## Keywords

### Declaration

- `var` - Used for declaring variables.
- `const` - Declares a constant variable.
- `function` - Declares a function.
- `thematic` - Declares a thematic block (needs clarification in usage).
- `statement` - Declares a standalone statement block.

### Classes

- `class` - Declares a class.
- `new` - Instantiates an object from a class.
- `this` - References the current instance.
- `super` - Calls a method from a parent class.
- `extends` - Enables inheritance between classes.
- `static` - Declares a static member of a class.

### Error Handling (Not Implemented)

- `try` - Attempts code that may throw an error.
- `catch` - Handles errors from a `try` block.
- `finally` - Executes cleanup code after `try` or `catch`.
- `throw` - Throws an error.

### Control Flow

- `if` / `else` - Conditional branching.
- `for` - Loop over ranges or collections.
- `while` / `do` - Loop with condition checking.
- `never` - Ensures a code path should never execute.
- `switch` / `case` / `default` - Multi-branch selection.
- `break` / `continue` - Loop control statements.
- `return` - Returns a value from a function.
- `when` - Provides conditional execution.

### Import & Export

- `import` - Imports modules or components.
- `export` - Exports modules or components.
- `from` - Specifies the source for imports.

### Special Control Flow

- `del` - Deletes variables or object properties.
- `unpack` - Extracts data from arrays or objects.
- `watch` - Observes changes to variables or properties.
- `defer` - Schedules tasks to run after scope exit.

### Unary Operators

- `typeof` - Returns the type of a value.
- `copyof` - Creates a copy of a value.
- `not` - Logical negation.
- `memoize` / `dememoize` - Manage cached function results.
- `identity` - Returns its operand unchanged.

### Binary Operators

- `in` / `not in` - Membership test.
- `as` - Casts a value to another type.
- `of` - Checks ownership or belonging.
- `and` / `or` / `nand` / `nor` / `xor` - Logical operators.
- `instanceOf` / `not instanceOf` - Tests type relationships.
- `is` / `is not` - Equality and inequality checks.

## Identifiers

### Description
- Must start with a letter, underscore, or dollar sign.
- Can contain letters, digits, underscores, and dollar signs.
- Cannot include spaces or special characters.
- Reserved keywords cannot be used as identifiers.

### Examples
- `hypermatrix`
- `hypermatrix1`
- `_hypermatrix`
- `$hypermatrix`

### Reserved Identifiers

Reserved for internal use or object member expressions:
- `true`, `false`, `null`, `undefined`
- `NaN`, `Infinity`, `_Infinity`
- `this`, `super`

These identifiers are not currently reserved but using them may lead to issues

### Row Identifiers

Enable precise function or member references by signature:

```hypermatrix
// Assigning a specific function
var SUM = #["sum(int, int)"];

// Using the identifier
println(SUM(1, 2)); // Output: 3
println(sum(1, 2) === SUM(1, 2)); // true

// Function definition
function sum(int a, int b) {
    return a + b;
}
```

## Comments

### Types of Comments

- **Single-line**: `// This is a comment.`
- **Multi-line**:
  ```
  /*
  Multi-line comments span
  multiple lines.
  */
  ```
- **Documentation**:
  ```
  /**
   * This documents a function or class.
   */
  ```
- **Section**: Enhances organization in code blocks.
  Section comments are used to group related code sections for better organization.
  They must be visually distinct in IDEs to enhance readability.

  Format rules:
  1. Start with at least three tildes: ~~~
  2. Can optionally start with pipe: |~~~
  3. Must end with at least three tildes: ~~~
  4. Can optionally end with pipe: ~~~|

  Examples:
  - `~~~ Section Name ~~~`
  - `|~~~ Section Name ~~~`
  - `~~~ Section Name ~~~|`
  - `|~~~ Section Name ~~~|`

  You can write code after a pipe-ended section:
  `~~~~~~~ Print ~~~~~~~| println("Hello, World!"); // This will print "Hello, World!"`

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

- **String**: `'string'`, `"string"`, ``string``
- **Numeric**: `123`, `123.45`
- **Intger**: `123`
- **Float**: `123.45`
- **Boolean**: `true`, `false`
- **Array**: `[1, 2, 3]`
- **Tuple**: `(1, 2, 3)`
- **Set**: `<1, 2, 3>`
- **Matrix**: `M[1, 2] | [3, 4]`
- **Object**: `{key: value}`

## Patterns

### Object Patterns

```hypermatrix
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

### Array Patterns

```hypermatrix
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

### Tuple Patterns

```hypermatrix
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

### Params Pattern

Used only in function, statement, and other parameters.

```hypermatrix
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


## Units (Experimental)

Units provide shorthand for multiplying numbers by predefined constants (e.g., `1m = m * 1`).

```hypermatrix
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
```

## Error Handling (In Progress)

Error handling is in its early stages and currently supports basic Syntax and Runtime Errors. Future updates will include custom exceptions and error propagation mechanisms.

```hypermatrix
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

## Watchers (Experimental)

Watchers allow observing and reacting to changes in variables, arrays, or object properties. This feature is experimental and will improve over time.

```hypermatrix
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

arr.push(6); // Prints: "push -> 6"
arr.pop();   // Prints: "remove -> 6"
arr = [1, 2, 3, 4, 5]; // Prints: "changed to -> [1, 2, 3, 4, 5]"
```

## Defers

Defers allow you to schedule code execution for later, even after the current function has returned. They are useful for cleanup tasks or resource management.

> Note: Defers execute at the end of their scope and have access to all variables within that scope.

```hypermatrix
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

// Result:
// Program
// Block
// block defer
// the sum = 11
// 11
// defer
// program defer
```

## Unpack (In Progress)

Unpack extracts values from arrays or objects into variables for easier and more concise code.

```hypermatrix
// Example using a built-in object
unpack (system) {
    println(screenWidth);
    println(screenHeight);

    keyPrint("windows", "tab");
}

var arr = [1, 2, 3, 4, 5];

unpack(arr) {
    println(_0_); // 1
    println(_2_); // 3
    println(_4_); // 5
}
```
## Build-in Functions

### **Print**
Prints any value to the console without adding a newline.
```hypermatrix
print(...values);
```

### **Println**
Prints any value to the console and adds a newline.
```hypermatrix
println(...values);
```

### **Input**
Gets user input from the terminal.
```hypermatrix
input(before, after);
```

### **Eval**
Evaluates a string as HyperMatrix code.
```hypermatrix
eval(code);
```

## Build-in Objects

### **System Object**

The `System` object provides access to various system-level operations and properties.

#### **Timer Functions**
- `System.setTimeout(callback, delay)`: Executes a function after a specified delay.
- `System.setInterval(callback, delay)`: Repeatedly calls a function with a fixed time delay.
- `System.setDoInterval(callback, delay)`: Like `setInterval`, but executes the callback immediately before starting.
- `System.nextFrame(callback)`: Executes a function on the next animation frame.
- `System.sleep(milliseconds)`: Pauses execution for the specified duration.

#### **Time Management**
- `System.startTimer()`: Starts recording elapsed time.
- `System.stopTimer()`: Stops the timer and returns the elapsed time.
- `System.now()`: Returns the current timestamp.

#### **Clipboard Operations**
- `System.setClipBoard(text)`: Sets the clipboard text.
- `System.getClipBoard()`: Retrieves the current clipboard text.

#### **System Utilities**
- `System.beep()`: Plays a system beep sound.
- `System.wait()`: Waits for user input.
- `System.exit()`: Terminates the program.

#### **Monitor and Screen Properties**
- `System.monitorWidth`: Width of the primary monitor.
- `System.monitorHeight`: Height of the primary monitor.
- `System.monitorRate`: Refresh rate of the monitor.
- `System.screenWidth`: Width of the screen.
- `System.screenHeight`: Height of the screen.
- `System.screenResolution`: Resolution of the screen.

#### **Desktop and Pixel Operations**
- `System.getDesktopProperty(propertyName)`: Retrieves a desktop property value.
- `System.pixelColor(x, y)`: Gets the color of the pixel at specified coordinates.

#### **Mouse Operations**
- `System.mouseLocation()`: Returns the current mouse position.
- `System.mouseMove(x, y)`: Moves the mouse cursor to specified coordinates.
- `System.mouseClick()`: Simulates a mouse click.
- `System.mouseClickAt(x, y)`: Clicks at specified coordinates.
- `System.mouseDoubleClickAt(x, y)`: Double-clicks at specified coordinates.
- `System.mouseWheel(amount)`: Simulates mouse wheel scrolling.
- `System.mousePress(...buttons)`: Simulates pressing mouse buttons.
- `System.mouseRelease(...buttons)`: Simulates releasing mouse buttons.

#### **Keyboard Operations**
- `System.keyPress(...keys)`: Simulates pressing keys.
- `System.keyRelease(...keys)`: Simulates releasing keys.
- `System.keyType(...keys)`: Simulates typing keys.
- `System.keyPrint(...keys)`: Simulates pressing multiple keys simultaneously, then releases them all.

#### **Future Enhancements**
More functions will be added soon to expand system capabilities.

---

### **Terminal Object**

The `Terminal` object provides functionality for interacting with the command line interface.

#### **Text Output**
- `Terminal.print(...any)`: Prints text without adding a newline.
- `Terminal.println(...any)`: Prints text with a newline.

#### **User Input**
- `Terminal.input(before, after)`: Prompts the user for input.
- `Terminal.readHidden(before, after)`: Prompts for hidden input (e.g., passwords).

#### **Screen Operations**
- `Terminal.clear()`: Clears the terminal screen.
- `Terminal.pause(repeatPause)`: Pauses terminal execution until user interaction.
- `Terminal.ignore(numberOfChars)`: Ignores a specific number of input characters.

#### **Command-Line Arguments**
- `Terminal.args`: Retrieves command-line arguments passed to the program.

#### **Future Enhancements**
The terminal will support additional features:
- Text colors (foreground/background).
- Font styles (bold, italic, underline).
- Text markers and anchors for advanced text manipulation.
- Real-time text modifications and deletions.


## Build-in Classes


### Math Class

#### **Math Constants**
- **Math.HPI**: `1.570796326794897`
- **Math.PI**: `3.141592653589794`
- **Math.TAU**: `6.283185307179588`
- **Math.E**: `2.718281828459045`

#### **Math Functions**

- **`Math.abs(x)`**: Returns the absolute value of a number.
- **`Math.acos(x)`**: Returns the arccosine of a number.
- **`Math.asin(x)`**: Returns the arcsine of a number.
- **`Math.atan(x)`**: Returns the arctangent of a number.
- **`Math.atan2(y, x)`**: Returns the arctangent of the quotient of its arguments.
- **`Math.ceil(x)`**: Returns the smallest integer greater than or equal to a number.
- **`Math.clamp(value, min, max)`**: Returns a value clamped between `min` and `max`.
- **`Math.cos(x)`**: Returns the cosine of a number.
- **`Math.cosh(x)`**: Returns the hyperbolic cosine of a number.
- **`Math.exp(x)`**: Returns `e` raised to the power of a number.
- **`Math.floor(x)`**: Returns the largest integer less than or equal to a number.
- **`Math.hypot(x, y)`**: Returns the square root of the sum of squares of its arguments.
- **`Math.int(x)`**: Returns the integer value of a number.
- **`Math.log(x)`**: Returns the natural logarithm of a number.
- **`Math.log10(x)`**: Returns the base 10 logarithm of a number.
- **`Math.max(...values)`**: Returns the largest of zero or more numbers.
- **`Math.min(...values)`**: Returns the smallest of zero or more numbers.
- **`Math.onOff()`**: Returns a random `1` or `0`.
- **`Math.pow(x, y)`**: Returns `x` raised to the power of `y`.
- **`Math.random()`**: Returns a pseudo-random number between `0` and `1`.
- **`Math.round(x)`**: Rounds a number to the nearest integer.
- **`Math.sign(x)`**: Returns the sign of `x`, indicating whether `x` is positive, negative, or zero.
- **`Math.sin(x)`**: Returns the sine of a number.
- **`Math.sinh(x)`**: Returns the hyperbolic sine of a number.
- **`Math.sqrt(x)`**: Returns the positive square root of a number.
- **`Math.tan(x)`**: Returns the tangent of a number.
- **`Math.tanh(x)`**: Returns the hyperbolic tangent of a number.
- **`Math.toDegrees(x)`**: Converts radians to degrees.
- **`Math.toPoint(x, y)`**: Creates a point from `x, y` coordinates.
- **`Math.toRadians(x)`**: Converts degrees to radians.

#### **Future Enhancements**
- Advanced 2D/3D mathematical operations.
- Geometric transformations.
- Statistical calculations and complex number support.
- Specialized classes for 2D/3D math (e.g., `Math2D`, `Matrix2D`, `Vector2D`).

---

### Future Classes (Planned Features)

#### **TerminalMatrix Class (ASCII Canvas)**
- Status: Coming Soon

---

#### **Date Class**
- Status: Coming Soon

---

#### **Interval Class**
- Ideas Needed: Potential future addition for time-based intervals.

---

#### **Matrix Class (Temporary Name)**
- Status: Work in Progress

---

#### **Json Class**
- Status: Coming Soon

---

#### **File Class**
- Status: Coming Soon

---

#### **Console Class**
- Status: Coming Soon

---

#### **OS Class**
- Status: Coming Soon

---

#### **Matrix2D Class**
- Status: Coming Soon

---

#### **Matrix3D Class**
- Not sure if this is needed, but it could be a nice addition for advanced use cases.

# Expressions

## Type Expressions

### **1. General Types**

#### **Any (Default)**
Represents any type of value.
```hypermatrix
<any> = undefined
<any> = null
<any> = 1
<any> = "string"
<any> = [1, 2, 3]
<any> = <%AnyOtherType%>
```

#### **Auto (Type Detection)**
Automatically detects and assigns the type based on the value.
```hypermatrix
<any> >>> <auto> = 1   // auto becomes int
<any> >>> <auto> = 1.0 // auto becomes float
```

#### **Null and Undefined**
Special types for absence of value.
```hypermatrix
<any> >>> <null> = null
<any> >>> <undefined> = undefined
```

---

### **2. Number Types**

#### **Numeric Types**
Represents both integers and floating-point numbers.
```hypermatrix
<any> >>> <number> >>> <float> = 1.0
<any> >>> <number> >>> <float> >>> <int> = 1
```

#### **Special Number Types**
```hypermatrix
<any> >>> <number> >>> <float> >>> <NaN> = NaN
<any> >>> <number> >>> <float> >>> <Infinity> = Infinity
```

---

### **3. String Type**
Represents sequences of characters.
```hypermatrix
<any> >>> <string> = "hello"
<any> >>> <string> = ""
```

---

### **4. Boolean Type**
Represents true or false values.
```hypermatrix
<any> >>> <boolean> = true
<any> >>> <boolean> = false
```

---

### **5. Collection Types**

#### **Array Type**
```hypermatrix
<any> >>> <array> = [1, 2, 3]
<any> >>> <array> = ["hello", "world"]
```

#### **Tuple Type**
```hypermatrix
<any> >>> <tuple> = (1, 2)
<any> >>> <tuple> = (1, 2, [3, 4])
```

#### **Set Type**
```hypermatrix
<any> >>> <set> = <1, 2, 3>
<any> >>> <set> = <1, "a">
```

#### **Matrix Type**
```hypermatrix
<any> >>> <matrix> = M[1, 2, 3]
                     |[4, 5, 6]
                     |[7, 8, 9]
```

---

### **6. Object Type**
Represents key-value pairs.
```hypermatrix
<any> >>> <object> = {a: 1, b: 2}
<any> >>> <object> = {key: "value"}
```

---

### **7. Function Types**

#### **Named Functions**
```hypermatrix
function sum(a, b) {
    return a + b;
}
```

#### **Anonymous Functions**
```hypermatrix
<any> >>> <Function> >>> <AnonymousFunction> = (a, b) -> a + b
```

---

### **8. Custom Types**

#### **Thematic Types**
Defines logical groupings with specific behavior.
```hypermatrix
thematic fullname {
    return "Hyper" + "Matrix";
}
```

#### **Statements**
Defines blocks with structured logic.
```hypermatrix
statement loop: block {
    ~> (int times = 10) {
        for (int i = 0; i < times; i++) {
            block({index: i});
        }
    }
}
```

---

### **9. Miscellaneous**

#### **Native Types**
Directly tied to the language’s core.
- `NativeFunction`
- `NativeStatement`
- `NativeThematic`

#### **Blocks**
```hypermatrix
// Regular Block
{
    println("Hello World");
}

// Single-Line Block
println("Hello World");

// Empty Block
{}
```

## Number Expressions

### **Binary Operators**
```hypermatrix
5 + 5 = 10
5 - 5 = 0
5 * 5 = 25
5 / 5 = 1
7 % 5 = 2
5 ** 5 = 3125

5 + 5 * 5 = 30 -> 5 + (5 * 5)
(5 + 5) * 5 = 50
```

### **Unary Operators**
```hypermatrix
+4 = 4      // Positive
-4 = -4     // Negative
++4 = 5     // Increment
--4 = 3     // Decrement
%%4 = 16    // Squaring
```

### **Prefix Operators**
```hypermatrix
4++ = 4 // Post-increment, value updates to 5 after use
4-- = 4 // Post-decrement, value updates to 3 after use
4%% = 4 // Post-squaring, value updates to 16 after use
```

### **Comparison Operators**
```hypermatrix
5 > 4 = true
5 < 4 = false
4 >= 4 = true
5 <= 4 = false
5 == 5 = true
5 != 5 = false
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
```

---

## String Expressions

### **Binary Operators**
```hypermatrix
"Hyper" + "Matrix" = "HyperMatrix"
"Matrix" + " " + "Grammar" = "Matrix Grammar"
"HyperMatrix" - "r" = "HypeMatix"
"Hello, World" * "o" = "HellO, WOrld"
"Hello, World" / "o" = "Hell _, W _rld"
```

### **Comparison Operators**
```hypermatrix
"hello" == "hello" = true
"5.236" == 5.236 = true
"hello" != "hello" = false
"5.236" != 5.236 = false
"HeLlo" ~= "hello" = true
"HeLlo" !~= "hello" = false
```

---

## Boolean Expressions

### **Binary Operators**
```hypermatrix
true + true = true
true + false = true
5 + true = 6
5 - false = 5
5 * true = 5
5 * false = 0
```

### **Comparison Operators**
```hypermatrix
true == true = true
true !== "true" = true
true >= false = true
false <= true = true
```

---

## Solid Operators

### **Binary Operators**
```hypermatrix
null ?? "hello" = "hello"
undefined ?? "hello" = "hello"
true || false = true
false && true = false
1 || 2 = 1
0 || 3 = 3
```

### **Unary Operators**
```hypermatrix
!true = false
!false = true
typeof true = boolean
typeof "ok" = string
copyof 1 = 1 // Creates a new pointer
identity true = {"type": "boolean", "value": true}
```

---

## Advanced Features

### **Memoization**
```hypermatrix
memoize 5 * 5 + 5 = 30 // Save for later
5 * 5 + 5 = 30 // Returns saved result
memoize factorial(5) = 120 // Save for later
```

### **Dememoization**
```hypermatrix
dememoize 5 * 5 + 5 = 30 // Recalculates and deletes saved result
dememoize factorial(5) = 120 // Recalculates and deletes saved result
```

## Defnitions

### **Type Definition**

#### **Boolean**
```hypermatrix
true
false
```

#### **Integer**
```hypermatrix
1
0
-1
-9223372036854775808 // min int64
9223372036854775807  // max int64
```

#### **Float**
```hypermatrix
1.0
0.0
-1.0
-1.7976931348623157e+308 // min float64
1.7976931348623157e+308  // max float64
```

#### **String**
```hypermatrix
""
"Hello World"
"Hello\nWorld"
"Hello\tWorld"
"Hello\rWorld"
"\u0126"
```

#### **FString**
```hypermatrix
F""
F"Hello #{\"World\" * 5}" = "Hello WorldWorldWorldWorldWorld"
F"#{"Hello" * 5} #{"World" * 5}" = "HelloHelloHelloHelloHello WorldWorldWorldWorldWorld"
F"#{F"#{F"#{F"#{F"#{"Hello World"}"}"}"}"}" = "Hello World"
```

### **Array**
```hypermatrix
[]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
[[1, 2, 3], [4, 5, 6], [7, 8, 9]]
["string", true, 1, 1.5, [1, 2, 3], {"key": "value"}]
```

### **Tuple**
```hypermatrix
(1, 2)
(1, 2, 3, 4, 5, 6, 7, 8, 9)
([1, 2, 3], [4, 5, 6], [7, 8, 9])
("string", true, 1, 1.5, [1, 2, 3], {"key": "value"}, (1, 2, 3))
```

### **Set**
```hypermatrix
<>
<1, 2, 3>
<[1, 2, 3], [4, 5, 6], [7, 8, 9]>
<"string", true, 1, 1.5, [1, 2, 3], {"key": "value"}, (1, 2, 3), <1, 2, 3>>
```

### **Matrix**
```hypermatrix
M[]
M[1, 2, 3]
 |[4, 5, 6]
 |[7, 8, 9]

M[1, 0.5, true]
 |["Hello", false, [F"Name: #{name}", 2.5, false]]
 |[(1, true, "OK"), <0.1, 0.2, 0.5>, M[1, 2] | [3, 4]]

M[1]               M[1, null, null]
 |[2, 3]           |[2, 3, null]
 |[4, 5, 6] same as |[4, 5, 6]
```

### **Object**
```hypermatrix
{}
{"key": "value"}
{"key": "value", key2: "value2"}
{key, "ey2": "value2", "key3": "value3"}
```

---

### **Anonymous Function**
```hypermatrix
() -> {}
function() {}
a -> {}
(a, b) -> {}
(a, b) -> a + b
(a, b) -> { return a + b }
function(a, b) { return a + b }
function(a) a * a
```

### **Anonymous Thematic**
```hypermatrix
thematic {
    return "hello, world!";
} value {
    println("Hello World" + value);
}

thematic: string {
    return "hello, world!";
} value {
    println("Hello World" + value);
}

thematic: string {
    return "hello, world!";
} value: string {
    println("Hello World" + value);
}

thematic: string {
    return "hello, world!";
} string value {
    println("Hello World" + value);
}
```

### **Anonymous Statement**
```hypermatrix
statement: block {
    ~> (n) {
        if (n > 0) {
            println("positive");
        } else if (n < 0) {
            this.isNegative();
        } else {
            this.isZero();
        }
    } isZero {
        println("zero");
    } isNegative {
        println("negative");
    }
}

statement: blk {
    ~> (n) {
        if (n > 0)
            blk({num: n});
        else this.isZero(n);

    } isZero(n) {
        if (n == 0)
            blk({num: n});
        else this.isNegative(n);

    } isNegative(n) {
        if (n < 0)
            blk({num: n});
    }
}

statement: block {
    ~> (int chance = 50) {
        block() when true.flip(chance) else this.Else();
    } Else {
        block();
    }
}

statement: block {
    ~> (int times = 10, int index = 0, update = 1) {
        for (int i = index; i < times; i += update) {
            block({index: i});
        }
    }
}
```


## Identifier

### **Syntax**
```hypermatrix
<identifier>

ident = ""
ident52 = ""
ident_52 = ""
_ident_52_ = ""
$ident = ""
$ident$52$ = ""
$ident_52$ = ""
_$ident = ""
```

---

## Row Identifier Expression

### **Syntax**
```hypermatrix
#[<string>]
```

### **Example**
Row identifiers allow referencing functions or members by their exact signature.
```hypermatrix
var newVar = #["sum(int, int)"];
```

---

## Member Expression

### **Syntax**
```hypermatrix
(<identifier> | <member>) . <identifier>
(<identifier> | <member>) . <call>
(<identifier> | <member>) . <member>
(<identifier> | <member>) . <memberCall>
```

### **Example**
```hypermatrix
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];

arr.length = 9;
arr.push(10);
```

## Call Expression

### **Syntax**
```hypermatrix
<identifier>()
<member>()
```

### **Example**
```hypermatrix
var func = () -> println("Hello World");

func();
system.wait(500);
```

## Assignment Expression

### **Syntax**
```hypermatrix
<identifier> = <expression>
<member> = <expression>
<pattern> = <expression>
```

### **Example**
```hypermatrix
var arr;

arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
arr.length = 5;
```

## As Expression

### **Syntax**
```hypermatrix
<identifier> as <identifier>
<member> as <identifier>
<call> as <identifier>
```

### **Example**
```hypermatrix
true as string = "true";
5 as string = "5";
5.0 as string = "5.0";
5.62 as int = 5;
5 as float = 5.0;
Math.PI as int = 3;
sum(5.7, 5.3) as int = 11;

const float PI = 3.14159;

int INT_PI = PI as int; // INT_PI = 3
```

---

## HashCast Expression

### **Syntax**
```hypermatrix
#<identifier> <identifier>
#<identifier> <member>
#<identifier> <call>
```

### **Example**
```hypermatrix
#boolean "" = false;
#boolean " " = true;
#int true = 1;
#int false = 0;
#int "1" = 1;
#int 1.0 = 1;
#int Math.OnOff() = 1 or 0;
sub(5, 5) as string = "0";
```

## Ternary Expression

### **Syntax**
```hypermatrix
<condition> ? <expression> : <expression>
<condition> ? <truecase> : <falsecase>
<condition> ? <truecase>
```

### **Example**
```hypermatrix
1 < 2 ? 1 : 2 = 1;
Math.random() > 0.5 ? "Head" : "Tail" = "Head" or "Tail";
Math.round(5.5) == 6 ? "Up" : "Down" = "Down";
Math.random(0, 100) % 2 === 0 ? "Even" : "Odd" = "Even" or "Odd";
```

## When Expression

### **Syntax**
```hypermatrix
<expression> when <condition> else <expression>
<truecase> when <condition> else <falsecase>
<truecase> when <condition>
```

### **Example**
```hypermatrix
5 when 1 < 2 else 10 = 5;
"Head" when Math.random() > 0.5 else "Tail" = "Head" or "Tail";
"Up" when Math.round(5.5) == 6 else "Down" = "Down";
"Even" when Math.random(0, 100) % 2 === 0 else "Odd" = "Even" or "Odd";
```

## New Expression

### **Syntax**
```hypermatrix
new <identifier>(<expression>...)
new <class name>(<expression>...)
new <type name>(<expression>...) // ASAP :D
```

### **Example**
```hypermatrix
new Matrix(true, 50); // in progress...
new File("file.txt"); // not implemented
new Date(2023, 1, 1); // coming soon...
new <type name>(); // coming soon...
```

## Reverse Assignment Expression

### **Syntax**
```hypermatrix
<expression> => <identifier>
```

### **Example**
```hypermatrix
load("file.txt") => file;

var data;
var dataStr;

Json.toObject(dataString) => data;
Json.toString(data) => dataStr;

// Json class coming soon...
```

---

## ChainPipe Expression

### **Syntax**
```hypermatrix
(<identifier> | <member> | <call>)  |> <member>
                                    |> <memberCall>
                                    |> <member>
                                    |> <memberCall>

@return <expression> // the same start point of the chain
```

### **Example**
```hypermatrix
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];

println(arr); // [1, 2, 3, 4, 5, 6, 7, 8, 9]

arr
|> add(10).add(10.5)
|> add(11)
|> add(12)
|> add(13)
|> pop()
|> add(14)
|> add(15);

println(arr); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 10.5, 11, 12, 14, 15]
```

## LinePersand Expression

## **Syntax**
```hypermatrix
(<identifier> | <member> | <call>)  &> <AnonymousFunction>
                                    &> <AnonymousFunction>
                                    &> <AnonymousFunction>
                                    &> <AnonymousFunction>

@return <expression> // result of the last anonymous function
```

## **Example**
```hypermatrix
var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];

println(arr); // [1, 2, 3, 4, 5, 6, 7, 8, 9]

var newArr = arr
             &> nums -> nums.filter(b -> b % 2 === 0) // filter any non-even number
             &> nums -> nums.map(b -> b * 2); // double all numbers

println(newArr); // [4, 8, 12, 16]

var square = arr -> arr.map(n -> n * n); // define the square line-persand anonymous function

const number sum = newArr
                    &> square
                    &> #["sumOfAll(array)"];

println(sum); // 480

function sumOfAll(array arr): number {
    return arr.reduce((sum, n) -> sum + n);
}
```

# Statement

## Variable Declaration

### **Syntax**
```hypermatrix
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
```

## Function Declaration

### **Syntax**
```hypermatrix
function <identifier>(<paramspattern>) <block>
function <identifier>(<paramspattern>): <type> <block>

<type> <identifier>(<paramspattern>) <block>
```

## Thematic Declaration

### **Syntax**
```hypermatrix
thematic <identifier> <getblock> <identifier> <setblock>
thematic <identifier>: <gettype> <getblock> <identifier> <setblock>
thematic <identifier>: <gettype> <getblock> <identifier>: <settype> <setblock>
thematic <gettype> <identifier> <getblock> <identifier>: <settype> <setblock>
thematic <gettype> <identifier> <getblock> <settype> <identifier> <setblock>
```

## Statement Declaration

### **Syntax**
```hypermatrix
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
```

## Class Declaration

### **Syntax**
```hypermatrix
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
```

## If Statement

### **Syntax**
```hypermatrix
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
```

## Switch Statement

### **Syntax**
```hypermatrix
switch (<expression>) {
    case <expression>: <inCaseBlock>
    break
    case <expression>: <inCaseBlock>
    break
    default: <inCaseBlock>
}

switch (<expression>): <comparison> {
    case <expression>: <inCaseBlock>
    break
    default: <inCaseBlock>
}
```

## For Statement

### **Syntax**
```hypermatrix
for (<initstatement>; <condition>; <updateexprsion>) <block>
for (<variabledeclaration> of <expression>) <block>
for (<variabledeclaration> in <expression>) <block>
```

## While Statement

### **Syntax**
```hypermatrix
while (<condition>) <block>

while (<condition>) <block>
never <block>
```

## Do While Statement

### **Syntax**
```hypermatrix
do <block> while (<condition>)
```

## Try Statement (Not Implemented)

### **Syntax**
```hypermatrix
try <block>
catch (<expression>) <block>
finally <block>
```

## Watch Statement (Experimental)

### **Syntax**
```hypermatrix
watch <expression> <block>
```

## Defer Statement

### **Syntax**
```hypermatrix
defer (<expression delayInMillis>) <block>
defer <block>
```

## Unpack Statement

### **Syntax**
```hypermatrix
unpack (<expression>) <block>
```

## Break Statement

### **Syntax**
```hypermatrix
break
break when <condition>
```

## Continue Statement

### **Syntax**
```hypermatrix
continue
continue when <condition>
```

## Return Statement

### **Syntax**
```hypermatrix
return <expression>
return when <condition>: <expression>
return when <condition>
return when <condition>; // return undefined
```

## Throw Statement (Not Implemented)

### **Syntax**
```hypermatrix
throw <expression>
throw when <condition>: <expression>
throw when <condition>
throw when <condition>; // stop program and throw default error
```

## Del Statement

### **Syntax**
```hypermatrix
del <identifier>
del <identifier>, <identifier>, ...
del <member>
del <identifier>, <member>, <member>, ...
del <tuplepattern>
```

## Import Statement

### **Syntax**
```hypermatrix
import <string>
import from <string>
import <objectpattern> <string>
import * <string>
import <objectpattern> as <identifier> <string>
```

## Export Statement

### **Syntax**
```hypermatrix
export <identifier>
export <declaration>
export <objectpattern>
```

## Block Statement

### **Syntax**
```hypermatrix
{
    <anystatement>...
}
```


# Archetypes

Archetypes enable prototype-like behavior for both native and user-defined types.
Current implementation supports basic archetype functionality.

## Key Features:
- Provides foundational prototype functionality.
- Facilitates extension and customization of native and custom types.
- Designed to simplify object behavior modeling.

## Implementation Notes:
- To inspect the archetype of a value, use the `__arche__` property.
- User-defined archetypes are under development and will be enhanced in future releases.
- The current implementation is basic, but a more robust version is planned for upcoming updates.


# HyperMatrix Programming Language

## About the Name

HyperMatrix combines two key concepts:
- **"Hyper"**: Represents a high-level programming language designed for ease of use for both beginners and experts.
- **"Matrix"**: Highlights its specialized support for matrix-like operations and data structures, complete with extensive built-in functions.

### Why "HyperMatrix"?
- A high-performance programming language optimized for matrix operations, applications, and games.
> Note: While current performance metrics are not finalized, future versions aim to deliver significant performance improvements.

---

## **Development Team**

**Lead Developer**: @DreamProgrammer

---

## **Project Timeline**

- **Start Date**: 2024-10-04
- **Completion Date**: 2024-12-11

---

## Release History

### Version 1.0.0
- **Release Date**: 2025-01-05
- Initial public release.
- Bug fixes and stability improvements.
- Function naming improvements and standardization.

# Note from the Creator
Thank you for exploring the HyperMatrix programming language! This is just the beginning of what I envision as a powerful and accessible tool for developers.

Continuous Improvement: All the features described here are part of the initial release and will be improved and expanded over time. Your feedback and suggestions are invaluable in shaping the future of this language.
Join the Journey: If you’re passionate about programming languages and would like to contribute to HyperMatrix, I’d be thrilled to have you join the project. Whether it’s coding, testing, or documentation, your help is welcome!
Feel free to reach out or contribute through the project’s repository. Together, we can make HyperMatrix something truly special.

- DreamProgrammer
---
