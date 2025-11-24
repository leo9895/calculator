**// src/app/calculator/calculator.component.ts
import { Component } from '@angular/core';

@Component({
  selector: 'app-calculator',
  templateUrl: './calculator.component.html',
  styleUrls: ['./calculator.component.css']
})
export class CalculatorComponent {
  number1: number | null = null;
  number2: number | null = null;
  result: number | string = '';

  calculate(operation: string) {
    const n1 = Number(this.number1);
    const n2 = Number(this.number2);

    // Basic validation: ensure inputs are numbers
    if (isNaN(n1) || isNaN(n2)) {
      this.result = 'Enter valid numbers';
      return;
    }

    switch (operation) {
      case 'add':
        this.result = n1 + n2;
        break;
      case 'subtract':
        this.result = n1 - n2;
        break;
      case 'multiply':
        this.result = n1 * n2;
        break;
      case 'divide':
        if (n2 === 0) {
          this.result = 'Cannot divide by zero';
        } else {
          this.result = n1 / n2;
        }
        break;
      default:
        this.result = '';
    }
  }

  // optional: clear inputs and result
  clear() {
    this.number1 = null;
    this.number2 = null;
    this.result = '';
  }
}
**
