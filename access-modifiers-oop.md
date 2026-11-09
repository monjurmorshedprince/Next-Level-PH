
Demystifying Access Modifiers in TypeScript OOP


Introduction

When building classes in JavaScript, everything is exposed by default. Anybody can reach in and change your internal variables. TypeScript fixes this by introducing Access Modifiers: `public`, `private`, `protected`, and `readonly`. These tools allow you to enforce boundaries, protecting your internal logic from accidental outside interference.



Public and Private Boundaries

By default, every property in a TypeScript class is `public`. It can be accessed and modified from anywhere. However, if you mark a property as `private`, it becomes completely locked down. It can only be accessed from inside the exact class where it was defined.

```typescript
class BankAccount {
  public accountHolder: string;
  private balance: number; //HIDDEN 

  constructor(name: string, initialDeposit: number) {
    this.accountHolder = name;
    this.balance = initialDeposit;
  }
}
```

Protected and Readonly

The protected modifier is like a VIP pass. It acts exactly like private, but with one exception: classes that inherit from the parent class (using extends) can still access it. Finally, readonly is used when a property can be seen by anyone, but can never be changed after it is set in the constructor.

class Employee {
  protected employeeId: string; 
  readonly hireDate: Date;      
}


Conclusion

Access modifiers are the backbone of solid Object-Oriented design in TypeScript. By thoughtfully applying private to hide internal states, protected for inheritance, and readonly for constants, you create robust code that is much harder for other developers to accidentally break.
