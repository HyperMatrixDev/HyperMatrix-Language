# Commands  

## HMatrix Command  

The `hmatrix` command is your gateway to executing `.hm` files or entering interactive sessions.  

### Syntax  
```bash
hmatrix <path> <args>      # Run a file with arguments  
hmatrix <path>             # Run a file  
hmatrix -continue <path>   # Run a file and enter interactive mode  
hmatrix                    # Start an empty interactive session
```
---

### Examples

Run `hello-world.hm` file  
```bash
hmatrix hello-world.hm
```  

Run `hello-world.hm` without specifying the `.hm` extension  
```bash
hmatrix hello-world  
```
Run `"hello-world.hm"` with arguments `["bold", "O K"]`
```bash
hmatrix hello-world.hm bold "O K"
```

Run `hello-world.hm` in interactive mode  
```bash
hmatrix -continue hello-world  
```

Start an empty interactive session
```bash
hmatrix
```


