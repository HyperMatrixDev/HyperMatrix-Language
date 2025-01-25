# Dev Goals

Welcome to the **HyperMatrix Development Goals** page! Here, you'll find updates on what we're working on, what's been released, and how you can join us in shaping the future of the HyperMatrix language.

---

## Releases

### **Upcoming Version 1.0.5**
> Details will be filled in soon with new features, fixes, and improvements currently in development.

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
