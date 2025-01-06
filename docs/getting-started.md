# Getting Started with HyperMatrix

Welcome to **HyperMatrix**, a high-level programming language designed to combine simplicity, flexibility, and innovation. This guide will help you install HyperMatrix and learn how to use its commands effectively.

---

## Installation

### Step 1: Download the Installer
1. Go to the [Releases](https://github.com/YourUsername/HyperMatrix/releases) section of the HyperMatrix repository.
2. Download the appropriate installer for your operating system.

### Step 2: Run the Installer
1. Run the downloaded installer file.
2. Follow the on-screen instructions to complete the installation.

Once installed, you can use the `hmatrix` command in your terminal.

---

## Using the `hmatrix` Command

The `hmatrix` command is the main way to execute HyperMatrix programs and access its interactive features. Below are the different ways to use it:

### **1. Run a File**
Execute a HyperMatrix file with or without arguments:
```bash
hmatrix <path-to-file> <args>
```
**Example**:
```bash
hmatrix hello-world.hm
```

### **2. Interactive Mode**
Start an interactive session to experiment with code:
```bash
hmatrix
```
This opens an empty interactive session where you can:
- Define variables.
- Execute code snippets.
- Test small programs.

### **3. Continue Mode**
Run a file and stay in interactive mode after it finishes execution:
```bash
hmatrix -continue <path-to-file>
```
While in continue mode, you can:
- Access variables defined in the file.
- Execute additional code.
- Run other files using the `run` command.

**Example**:
```bash
hmatrix -continue demo-file.hm
```

After the file executes, you can:
```bash
> println(myVar); // Access a variable defined in the file
> run another-file.hm; // Run another file
```

---

## Writing Your First Program

1. Create a file named `hello-world.hm`:
   ```hm
   println("Hello, World!");
   ```

2. Run the file using the `hmatrix` command:
   ```bash
   hmatrix hello-world.hm
   ```

3. Expected output:
   ```
   Hello, World!
   ```

---

## Exploring Examples

HyperMatrix comes with several example programs to demonstrate its features. You can find them in the `examples/` directory:

- **`hello-world.hm`**: A basic Hello World program.
- **`paint-heart.hm`**: Drawing a heart in windows 11 paint.

Run these examples using:
```bash
hmatrix <path-to-example>
```

---

## Getting Help

If you encounter issues or have questions:
- Refer to the documentation files in the `docs/` directory.
- Open an issue on the GitHub repository.

Thank you for using HyperMatrix! We’re excited to see what you create.
