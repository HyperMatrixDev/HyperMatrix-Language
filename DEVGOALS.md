# Dev Goals

Welcome to the **HyperMatrix Development Goals** page! Here, you'll find updates on what we're working on, what's been released, and how you can join us in shaping the future of the HyperMatrix language.

---

## Releases

### **Upcoming Version 1.0.8**
> Details will be filled in soon with new features, fixes, and improvements currently in development.

## **Version 1.0.7 - Stability Update (Completed)**
[View Release on GitHub](https://github.com/HyperMatrixDev/HyperMatrix-Language/releases/tag/v1.0.7)

#### **Fixes and Improvements:**
- **Block Parsing Fixes**: Resolved issues related to incorrect parsing of block bodies.
- **Enhanced Error Handling**:
  - Improved identifier tracking in error messages.
  - Error messages now provide more contextual details.
  - Overall error handling efficiency improved by **40%**.
- **Command Enhancements**:
  - Added `-version` flag to display the current HyperMatrix version (**highest priority flag**).
  - Added `-grammar` flag to retrieve the grammar file (**priority 4**).
  - Modified `-help` flag to display a basic usage guide instead of the full grammar.
- **Interactive Mode Enhancements**:
  - `run` now repeats the last executed file when used without arguments.
  - If no previous file exists, it shows correct usage guidance.
- **Expanded Escape Sequences**:
  - Added `\s` (non-breaking space) and `\z` (zero-width non-joiner).
  - New escape characters `{}`, `[]`, and improved `\C[...]` rainbow text.
- **Performance Optimizations**:
  - Parsing speed significantly improved by removing redundant checks and backtracking.
  - Optimized binary, octal, and hex escapes for efficiency.
- **Unicode & Symbol Enhancements**:
  - Introduced over **100 new Unicode character escapes**, including symbols, chess pieces, arrows, emojis, and more.


### **Version 1.0.6 - Lexer & Parser Update (Completed)**  
[View Release on GitHub](https://github.com/HyperMatrixDev/HyperMatrix-Language/releases/tag/v1.0.6)  

#### Updates and Enhancements:

### Lexer and Parser Overhaul
- **Rebuilt the lexer** for better efficiency and flexibility.
- **Rebuilt the parser** to enhance usability and future-proofing.
- **Prepared the lexer and parser** for upcoming syntax settings updates.

### Expanded Numeric Support
- Added lexing for:
  - **Binary numbers** (`0b100110`)
  - **Hexadecimal numbers** (`0xfe14d5`)
  - **Octal numbers** (`0o521237`)
  - **Numbers with exponents** (`45e+2`)

### Multi-Word Keywords
- Introduced flexible keyword combinations:
  - `hash tag` (both words form a keyword, individually they are not)
  - `is not` (each is a keyword, but together they form another keyword)
  - `is null` (the first is a keyword, the second is not, but together they form a new keyword)

### Static Initializers
- Added **static initializers for classes**, similar to Java:
  ```hypermatrix
  class Example {
      static {
          println("Static block initialized");
      }
  }
  ```
  - Allows initializing static variables multiple times within a class.
  - Executes in the order defined.

### Stable Unit Expressions
- **Unit expressions** are now stable and fully supported.
- Works with numeric types:
  ```hypermatrix
  45m      // Integer with unit
  5.3cm    // Float with unit
  0b100110turn // Binary number with unit
  ```

### Performance Enhancements
- Optimized `switch` and `if` statements, making execution **76% faster**.
- Fixed infinite loop bug caused by unclosed parenthesis `(5`, which now properly throws an error.

### AST Serialization Support
- Added `.hpr` file format (**High Performance Load**), enabling **fast execution without lexing or parsing**.

### Extended Escape Character Support
- Vastly expanded escape sequences, including:
  - **Unicode & Hexadecimal Support**: `\uXXXX`, `\xXX / \x{XXXX}`
  - **Text Formatting & Colors**: `\|color|text`, `\|#RRGGBB|text`, `\|##RRGGBB|text`
  - **Randomized Characters**: `\?;`, `\?{abcde};`, `\???`
  - **Repetition & Control Sequences**: `\#Nchar;`, `\#N{text};`, `\D{format}`, `\T{format}`

---

### **Development Goals**

### Upcoming Enhancements
- **Syntax Settings Update**:
  - Introduce customizable syntax configurations.
  - Improve handling of user-defined syntax rules.

- **Performance Optimization**:
  - Reduce memory usage further by refining parser execution.
  - Improve AST deserialization for even faster `.hpr` execution.

- **Better Debugging Support**:
  - Implement detailed error messages with suggested fixes.
  - Expand interactive debugging capabilities.

---

Thank you for supporting HyperMatrix! Your feedback helps us refine and expand the language. Feel free to contribute suggestions or report issues on our [GitHub Issues](https://github.com/HyperMatrixDev/HyperMatrix-Language/issues).


### **Version 1.0.5 (Skipped)**  
This version was skipped as it was dedicated to extensive lexer testing and validation. Improvements and optimizations from this phase have been incorporated into version 1.0.6 for public release.

### **Version 1.0.4 (Completed)**  
[View Release on GitHub](https://github.com/HyperMatrixDev/HyperMatrix-Language/releases/tag/v1.0.4)  

#### Updates and Enhancements:

### Shell Updates
- **Removed Color Support**: Eliminated colors in the shell and error messages to prevent issues with unsupported terminals displaying garbled text.
- **New Startup Message**: Added an informative startup message for a better user experience.

### New `hmatrix` Command Flags
- **`-time`**: Displays the execution time of the program.
- **`-lib:<path>`**: Attaches a library folder for the current run.
  - Example:
    ```bash
    hmatrix -lib:/path/to/lib myfile.hm
    ```
- **`-setup`**: Sets up a HyperMatrix project in the current folder or at a specified path.
  - Example:
    ```bash
    hmatrix -setup:/path/to/project
    ```
- **`-settings:<path>`**: Attaches a settings file for the current run (will be fully functional after lexer updates).
- **`-resource:<path>`**: Attaches resource files for the current run.
- **`-help`**: Displays grammar documentation in Markdown format and exits the program.

### Thematic `this` Fix
- Fixed an issue where the `this` keyword could not be used within thematic blocks.

---

#### Development Goals:

### Planned Enhancements

- **Flag Usability**:
  - Ensure all new flags (`-settings`, `-resource`) are fully functional and integrated with the lexer and runtime.

- **Interactive Shell Improvements**:
  - Enable persistent settings between `-continue` sessions.
  - Add enhanced error messages for invalid flag usage.

- **Documentation Improvements**:
  - Include detailed examples for new flags in both user guides and built-in help (`-help`).

- **Performance Tuning**:
  - Optimize shell execution for faster startup and reduced resource usage.

---

### **Version 1.0.3 (Completed)**  
[View Release on GitHub](https://github.com/HyperMatrixDev/HyperMatrix-Language/releases/tag/v1.0.3)  

#### Fixes and Improvements:

- **Class Instance Properties**: Fixed shared properties issue; instances now have independent properties.  
- **Function Display**: Corrected functions being shown as strings in the console.  
- **`this` Scope Binding**: `this` now properly binds to local scope variables.  
- **Interactive Mode**: Resolved issues with accessing instance variables in `-continue` mode.  
- **Instance Representation**: Instances show `stringify` method output or default object representation.  
- **Compiler/Lexer**: Faster stringification of values, better multi-line comment handling.  

#### Archetype Enhancements:

- **Memory Optimization**: Reduced memory usage with delayed unique archetype creation.  
- **Enhanced Functionality**: View and define archetypes:
  ```hypermatrix
  println(identity "Matrix");  // Outputs archetype details
  println("Matrix".__arche__); // String archetype object

  string.archetype.reverse = () -> this.split('').reverse().join('');
  println("Hyper".reverse()); // Outputs: repyH
  ```
#### New Features:

- **Improved Imports**: Native module importing with aliasing:
  ```hypermatrix
  import os as OS
  import "file.hm" as file
  import {newFile, delFile} as file from "file.hm"
  ```
- **printf Function**: Added formatted string output:
  ```hypermatrix
  printf("Hello, %s!", "World"); // Output: Hello, World!
  ```
---

### **Version 1.0.2 (Skipped)**  
This version was skipped as it focused on internal refactoring of archetypes and optimization work. Changes were included in version 1.0.3 for public release.

---

### **Version 1.0.1 (Completed)**  
[View Release on GitHub](https://github.com/HyperMatrixDev/HyperMatrix-Language/releases/tag/v1.0.1)  

#### Fixes and Improvements:
- **Class Declarations in Loops**: Resolved an issue where variables could not be declared within `while` scopes due to naming conflicts.
- **Reverse Assignments in Nested Scopes**: Fixed issues with reverse assignment expressions failing in nested scopes.
- **Logical Operator Behavior**:
  - Corrected functionality of `and` and `or` operators:
    - `or`: Now functions as a logical OR.
    - `and`: Now functions as a logical AND.
- **Assignment Evaluation**: Ensured assignments are evaluated only once to prevent unexpected behavior.
- **Control Flow Statements**: 
  - Updated `break`, `continue`, and `return` to properly stop the intended scope or loop instead of halting the entire program.
- **Multi-Line Strings**: Enhanced handling of multi-line strings wrapped in backticks (`` ` ``):
  - Leading spaces are trimmed to match the lowest indentation level.
  - New lines are removed if they appear at the beginning or end.
  - Added error messages for improper use of single (`'`) or double (`"`) quotes in multi-line strings.
- **Additional Enhancements**:
  - Improved support for the `undefined` type in logical comparisons with `is` and `is not`.
  - Enhanced error messages for better debugging clarity.

---

### **Version 1.0.0 (Completed)**  
[View Release on GitHub](https://github.com/HyperMatrixDev/HyperMatrix-Language/releases/tag/v1.0.0)  

- Initialized the **HyperMatrix language** and implemented the foundational features of the programming language.

---

## Community

### **Join the Team**
We’re always looking for passionate developers to help shape **HyperMatrix**! Whether you're a beginner or an experienced programmer, your contributions are welcome.

**Contact us**:  
📧 **dreamProgramer8691@hotmail.com**  

Together, we can make **HyperMatrix** the next big thing in programming!

---

## Notes
Stay tuned for more updates! This file will be updated regularly with our latest progress and goals.
