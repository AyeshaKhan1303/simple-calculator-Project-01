
# Command-Line Calculator

This project is a simple command-line calculator built using TypeScript. It allows users to perform basic arithmetic operations: addition, subtraction, multiplication, and division.

---

## Features

1. **Interactive Input**: Users can input two numbers and select an operator.
2. **Arithmetic Operations**: Supports addition, subtraction, multiplication, and division.
3. **Dynamic CLI**: Uses `inquirer` for an interactive command-line experience.

---

## Installation

1. Clone the repository:

   ```bash
   git clone <repository_url>
   cd <repository_directory>
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Compile TypeScript to JavaScript:

   ```bash
   npx tsc
   ```

---

## Usage

1. Run the calculator:

   ```bash
   node dist/index.js
   ```

2. Follow the prompts to:
   - Input two numbers.
   - Select an operator.

3. The result of the operation will be displayed in the terminal.

---

## Code Overview

### Main Logic

The calculator prompts the user for two numbers and an operator using the `inquirer` package:

```typescript
const answer = await inquirer.prompt([
    { message: "Enter first number", type: "number", name: "firstnumber" },
    { message: "Enter second number", type: "number", name: "secondnumber" },
    {
        message: "Select one of the operators to perform operation",
        type: "list",
        name: "operator",
        choices: ["Addition", "Subtraction", "Multiplication", "Division"],
    },
]);
```

Based on the selected operator, it performs the corresponding arithmetic operation:

```typescript
if (answer.operator === "Addition") {
    console.log(answer.firstnumber + answer.secondnumber);
} else if (answer.operator === "Subtraction") {
    console.log(answer.firstnumber - answer.secondnumber);
} else if (answer.operator === "Multiplication") {
    console.log(answer.firstnumber * answer.secondnumber);
} else if (answer.operator === "Division") {
    console.log(answer.firstnumber / answer.secondnumber);
} else {
    console.log("Please select a valid number");
}
```

---

## File Structure

```
Command-Line-Calculator/
├── node_modules/
├── src/
│   └── index.ts
├── dist/
│   └── index.js
├── package.json
├── tsconfig.json
└── README.md
```

---

## Dependencies

- **[inquirer](https://www.npmjs.com/package/inquirer)**: For interactive command-line prompts.

Install it using:

```bash
npm install inquirer
```

---

## Future Enhancements

1. Add support for more advanced operations like modulus and exponents.
2. Include error handling for invalid inputs, such as division by zero.
3. Allow multiple calculations in a single session.
4. Add a history feature to display previous calculations.

---

## License

This project is licensed under the MIT License. Feel free to use, modify, and distribute it.

---

## Contributing

Contributions are welcome! Feel free to submit a pull request or open an issue for suggestions and bug fixes.

---
