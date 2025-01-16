# Dev Goals

Welcome to the **HyperMatrix Development Goals** page! Here, you'll find updates on what we're working on, what's been released, and how you can join us in shaping the future of the HyperMatrix language.

---

## Releases

### **Upcoming Version 1.0.2**
> Details will be filled in soon with new features, fixes, and improvements currently in development.

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