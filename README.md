- 👋 Hi, I’m @zeenat00
CALCULATOR APP CODE ;

import inquirer from 'inquirer';

// Function to perform addition
function add(a: number, b: number): number {
  return a + b;
}

// Function to perform subtraction
function subtract(a: number, b: number): number {
  return a - b;
}

// Function to perform multiplication
function multiply(a: number, b: number): number {
  return a * b;
}

// Function to perform division
function divide(a: number, b: number): number {
  return a / b;
}

// Prompt the user for input
inquirer
  .prompt([
    {
      type: 'number',
      name: 'num1',
      message: 'Enter the first number:',
    },
    {
      type: 'number',
      name: 'num2',
      message: 'Enter the second number:',
    },
    {
      type: 'list',
      name: 'operation',
      message: 'Select an operation:',
      choices: ['Add', 'Subtract', 'Multiply', 'Divide'],
    },
  ])
  .then((answers) => {
    const num1 = answers.num1;
    const num2 = answers.num2;
    let result: number;

    switch (answers.operation) {
      case 'Add':
        result = add(num1, num2);
        console.log(`Result: ${result}`);
        break;
      case 'Subtract':
        result = subtract(num1, num2);
        console.log(`Result: ${result}`);
        break;
      case 'Multiply':
        result = multiply(num1, num2);
        console.log(`Result: ${result}`);
        break;
      case 'Divide':
        result = divide(num1, num2);
        console.log(`Result: ${result}`);
        break;
      default:
        console.log('Invalid operation');
        break;
    }
  });
