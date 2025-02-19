# Commands

## HMatrix Command

The `hmatrix` command is your gateway to executing `.hm` files or entering interactive sessions. It also supports various flags for enhanced functionality.

---

### Syntax
```bash
hmatrix <path> <args>         # Run a file with arguments
hmatrix <path>                # Run a file
hmatrix -continue <path>      # Run a file and enter interactive mode
hmatrix                       # Start an empty interactive session
hmatrix -time <path>          # Run a file and display execution time
hmatrix -lib:<path> <file>    # Attach a library folder and run a file
hmatrix -setup:<path>         # Setup a HyperMatrix project at the specified path
hmatrix -settings:<path> <file> # Attach settings file for the current run (lexer update required)
hmatrix -resource:<path> <file> # Attach resources for the current run
hmatrix -help                 # Display grammar documentation and exit
hmatrix -version              # Show version information (highest priority, overrides all other flags)
hmatrix -grammar              # Retrieve the grammar file (priority 4)
hmatrix -setup                # Setup a HyperMatrix project in the current directory (priority 3)
```

---

### Shell Enhancements
- **New priority-based command-line options:**
  - `-version` → Displays language version details (**priority 1**, overrides all other flags).
  - `-help` → Shows basic usage information (**priority 2**).
  - `-setup` → Initializes a project in the current or specified directory (**priority 3**).
  - `-grammar` → Retrieves the full grammar file (**priority 4**).
- **Interactive Mode Enhancements:**
  - `run` without arguments repeats the last executed file.
  - If no previous file exists, it displays proper usage guidance.

---

### Examples

#### Run `hello-world.hm` file
```bash
hmatrix hello-world.hm
```

#### Run `hello-world.hm` without specifying the `.hm` extension
```bash
hmatrix hello-world
```

#### Run `hello-world.hm` with arguments `bold` and `"O K"`
```bash
hmatrix hello-world.hm bold "O K"
```

#### Run `hello-world.hm` in interactive mode
```bash
hmatrix -continue hello-world
```

#### Start an empty interactive session
```bash
hmatrix
```

#### Display execution time after running `hello-world.hm`
```bash
hmatrix -time hello-world.hm
```

#### Attach a library folder and run `hello-world.hm`
```bash
hmatrix -lib:/path/to/lib hello-world.hm
```

#### Setup a HyperMatrix project in the current folder
```bash
hmatrix -setup
```

#### Setup a HyperMatrix project at a specified path
```bash
hmatrix -setup:/path/to/project
```

#### Attach settings and resources for the current run
```bash
hmatrix -settings:/path/to/settings -resource:/path/to/resources hello-world.hm
```

#### Display grammar documentation
```bash
hmatrix -help
```

#### Show the current version of HyperMatrix
```bash
hmatrix -version
```

#### Retrieve the grammar file
```bash
hmatrix -grammar
