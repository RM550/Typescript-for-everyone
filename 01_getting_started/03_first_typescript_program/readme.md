# 📌 TypeScript Project Setup & Compilation Guide 🚀

Welcome to this detailed guide on setting up and compiling a TypeScript project! 🎯 In this README, we will go through the process of creating a project, writing TypeScript code, and compiling it to JavaScript. Let’s dive in! 💡

---

## 📂 Project Setup

1. **Create a Project Folder** 🗂️
   - Navigate to your **Desktop** (or any preferred location).
   - Create a new folder, e.g., `hello-dash-work`.
   - Open this folder in **VS Code**.
   - You can simply **drag and drop** the folder into VS Code.

2. **Opening the Terminal in VS Code** 💻
   - Go to the **View** menu.
   - Click on **Terminal** (Shortcut: `Ctrl + Backtick (\``) on Mac).
   - This will open an integrated terminal at the project’s root.

---

## 🛠️ Installing TypeScript

To use TypeScript, install it globally using npm:

```sh
npm install -g typescript
```

Check the installed version:

```sh
tsc --version
```

If you see a version number, TypeScript is installed successfully! ✅

---

## ✍️ Writing TypeScript Code

Inside your project folder, create a new file: `index.ts` 📄

Now, let’s write some basic TypeScript code:

```typescript
// Declaring a variable with type annotation
let age: number = 25;

// Trying to assign a string to a number variable will cause an error
// age = "hello"; // ❌ Error: Type 'string' is not assignable to type 'number'

console.log(`My age is: ${age}`);
```

### 📝 Explanation:
- We declare a variable `age` and annotate it with `number`.
- If we try to assign a `string`, TypeScript will show an error. ❗
- This ensures **type safety** at compile time, preventing runtime errors.

---

## 🔧 Compiling TypeScript Code

To compile the TypeScript file into JavaScript, run:

```sh
tsc index.ts
```

This generates an **index.js** file with JavaScript code:

```javascript
var age = 25;
console.log("My age is: " + age);
```

### 💡 Why Compile?
- TypeScript adds type safety, but browsers understand only JavaScript.
- Compilation converts TypeScript into standard JavaScript for execution.

---

## 🛠️ Configuring TypeScript Compiler

To customize TypeScript compilation settings, create a **tsconfig.json** file:

```sh
tsc --init
```

This generates a default configuration file. Modify it as needed:

```json
{
  "compilerOptions": {
    "target": "ES6", // Target ECMAScript version
    "module": "CommonJS", // Module system
    "strict": true // Enables strict type checking
  }
}
```

Now, you can compile your code using:

```sh
tsc
```

This will compile all `.ts` files in the project!

---

## 🌍 JavaScript Specification vs Implementation

- **JavaScript is an implementation** of a specification called **ECMAScript (ES)**.
- **ES5** has been around for more than a decade and is widely supported in browsers. 🌎
- TypeScript helps developers write **cleaner, safer, and more maintainable** JavaScript by adding **static typing**.

---

## 📌 Next Steps 🚀

In the next lesson, we’ll:
- Learn how to configure the **TypeScript compiler** to target different JavaScript versions.
- Explore more **advanced TypeScript features**.

Stay tuned and happy coding! 🎉💻

