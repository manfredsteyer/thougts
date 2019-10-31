# DI 

```typescript

// Logic

export class BudgetService {
    constructor(private calc: Calc) { }
    calcBudget(year: number) { ... }
}

// Config
config({ provide: Calc, useClass: FastCalc });

// Execution

injectedBudgetService.calcBudget(2020);

```

# Currying 

```typescript

// Logic
const calcBudgetWithCalc = (calc: Calc) => (year: number) => {
    ...
}

// Config

export const ourCalc = fastCalc;
export const calcBudget = calcBudgetWithCalc(ourCalc);

// Execution

calcBudget(2020)

```