## Operational errors

Operational errors are **runtime errors** that occur due to predictable external factors or **conditions that the system cannot control** but should handle gracefully. These are problems that arise during the normal operation of the program and can be anticipated.

**Examples**:
- Network failures (e.g., connection lost)
- File not found
- Disk full or out of memory
- Timeout errors (e.g., API requests exceeding time limits)
- Invalid user input (e.g., missing required fields in a form)

```js
// Example of handling an operational error:
fs.readFile('nonexistentfile.txt', (err, data) => {
  if (err) {
    console.error('Operational error: File not found');
    // Handle error, e.g., send error message to user
  }
});
```

## Programmer Errors

Programmer errors are **bugs** in the code caused by **mistakes made by developers**. These are logic or coding errors that indicate incorrect assumptions about how the code should function.

**Examples**
- Syntax errors
- Reference errors (e.g., calling a function that doesn’t exist)
- Using an undefined variable
- Logic errors (e.g., incorrect conditional checks)
- Misuse of APIs (e.g., incorrect argument passed to a function)