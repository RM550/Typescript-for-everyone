# Debugging TypeScript Applications in VS Code 🚀

Debugging is an essential skill for every developer. When our TypeScript code doesn't work as expected, debugging allows us to step through the execution and identify issues. In this guide, we will explore how to effectively debug TypeScript applications in **Visual Studio Code (VS Code)**. 🛠️

---

## 📌 Why Debugging is Important?

When things go wrong in our TypeScript code, debugging helps us:
- **Find errors** in logic and syntax.
- **Analyze variable values** at different execution points.
- **Step through the code** line by line.
- **Understand how JavaScript is generated** from TypeScript.

---

## 🎯 Setting Up Debugging in VS Code

To debug TypeScript in **VS Code**, follow these steps:

### 1️⃣ Install Necessary Extensions
Ensure you have the **VS Code Debugger for JavaScript/TypeScript** extension installed.

### 2️⃣ Create a TypeScript File
Inside the `src` folder, create a file called **`index.ts`** and add the following logic:

```typescript
let age: number = 12;

if (age < 15) {
    age += 10;
}

console.log("Updated Age:", age);
```

### 3️⃣ Compile TypeScript Code
Since browsers cannot directly run TypeScript, we need to compile it to JavaScript. Run:

```sh
tsc index.ts
```

This generates a `index.js` file.

### 4️⃣ Configure Debugger in VS Code

1. Open **VS Code** and navigate to the `Run and Debug` section.
2. Click on `create a launch.json file`.
3. Select `Node.js`.
4. Modify the generated **`launch.json`** file:

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "node",
            "request": "launch",
            "name": "Launch Program",
            "program": "${workspaceFolder}/index.js",
            "preLaunchTask": "tsc: build - tsconfig.json"
        }
    ]
}
```

This configuration ensures that TypeScript is compiled before debugging.

---

## 🛑 Setting Breakpoints

Breakpoints allow us to **pause execution** at a specific line to inspect variables. To set a breakpoint:

1. Open `index.ts` in VS Code.
2. Click **left of the line number** where you want execution to stop.
3. A **red dot** (🔴) will appear, indicating a breakpoint.

Now, start debugging by clicking **Run -> Start Debugging** or pressing `F5`.

---

## 🛠️ Debugging Controls

Once debugging starts, use the following controls:

- ▶️ **Continue (F5):** Runs the program until the next breakpoint.
- ⏩ **Step Over (F10):** Executes the current line and moves to the next.
- 🔽 **Step Into (F11):** Steps into function calls.
- ⏏ **Step Out (Shift + F11):** Exits the current function.
- 🛑 **Stop (Shift + F5):** Stops debugging.
- 🔄 **Restart (Ctrl + Shift + F5):** Restarts the program.

---

## 🔍 Watching Variables & Expressions

### 1️⃣ Watch Window

- Open the `Watch` window in VS Code.
- Click `Add Expression` and enter a variable name (e.g., `age`).
- You can now track changes in `age` at every step.

### 2️⃣ Call Stack

This section shows the sequence of function calls that led to the current execution point.

### 3️⃣ Breakpoints Panel

Lists all breakpoints you’ve set.

---

## 💡 Debugging Example with Functions

Let’s add a function and see how to debug it.

```typescript
function updateAge(currentAge: number): number {
    if (currentAge < 15) {
        return currentAge + 10;
    }
    return currentAge;
}

let age = 12;
age = updateAge(age);
console.log("Updated Age:", age);
```

Set a **breakpoint** at `return currentAge + 10;` and use **Step Into (F11)** to jump inside the function.

---

## 🚀 Best Practices for Debugging TypeScript

✔️ Always use **strict mode** in `tsconfig.json`:
```json
{
  "compilerOptions": {
    "strict": true
  }
}
```

✔️ Use `console.log()` to quickly debug small issues.

✔️ Keep functions **small and modular** to make debugging easier.

✔️ Regularly **review logs and error messages** for clues.

✔️ Enable **source maps** for better debugging experience:
```json
{
  "compilerOptions": {
    "sourceMap": true
  }
}
```

---

## 🎯 Conclusion

With **VS Code debugging tools**, you can step through TypeScript code, inspect variables, and catch bugs early. Mastering these techniques will make you a more efficient developer! 🚀💻

Happy Debugging! 🛠️🔥

