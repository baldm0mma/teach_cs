## Lesson 03

### JavaScript Fundamentals: Syntax, Data Types, and Data Structures

#### Introduction (5 minutes)
In our first two lessons, we learned about binary and Boolean logic. Now we'll learn the fundamental building blocks of JavaScript: its syntax, data types, and data structures. Think of this as learning the vocabulary and grammar of a new language.

#### JavaScript Syntax Basics (15 minutes)

1. **Keywords and Variable Declaration**
   ```javascript
   // Variable declaration keywords
   let changeableVariable = 1;      // Block-scoped, can be reassigned
   const constant = 2;              // Block-scoped, cannot be reassigned
   var oldStyle = 3;               // Function-scoped (avoid using)

   // Other important keywords
   if (condition) {}               // Conditional
   for (let i = 0; i < 5; i++) {} // Loop
   while (condition) {}           // Another loop
   function name() {}             // Function declaration
   return value;                  // Return from function
   class MyClass {}              // Class declaration
   try {} catch {} finally {}    // Error handling
   import {} from 'module';      // Module import
   export default thing;         // Module export
   ```

2. **Operators**
   ```javascript
   // Arithmetic
   let sum = 5 + 3;        // Addition
   let diff = 10 - 4;      // Subtraction
   let product = 6 * 2;    // Multiplication
   let quotient = 15 / 3;  // Division
   let remainder = 17 % 5; // Modulus
   let power = 2 ** 3;     // Exponentiation

   // Assignment
   let x = 1;             // Basic assignment
   x += 2;                // Add and assign
   x -= 1;                // Subtract and assign
   x *= 3;                // Multiply and assign
   x /= 2;                // Divide and assign

   // Comparison
   let isEqual = 5 === 5;        // Strict equality
   let isNotEqual = 5 !== '5';   // Strict inequality
   let isGreater = 6 > 5;        // Greater than
   let isLessOrEqual = 4 <= 4;   // Less than or equal

   // Logical
   let and = true && false;      // Logical AND
   let or = true || false;       // Logical OR
   let not = !true;              // Logical NOT
   ```

3. **Functions**
   ```javascript
   // Function declaration
   function greet(name) {
       return `Hello, ${name}!`;
   }

   // Arrow function
   const greetArrow = (name) => `Hello, ${name}!`;

   // Function with default parameters
   function greetWithDefault(name = 'Guest') {
       return `Hello, ${name}!`;
   }

   // Rest parameters
   function sum(...numbers) {
       return numbers.reduce((total, num) => total + num, 0);
   }
   ```

4. **Template Literals and String Interpolation**
   ```javascript
   const name = 'Alice';
   const age = 25;
   console.log(`${name} is ${age} years old`);
   ```

#### Basic Data Types (10 minutes)

1. **Numbers**
   ```javascript
   // Integers
   let age = 25;
   let temperature = -5;
   
   // Floating point (decimals)
   let price = 19.99;
   let pi = 3.14159;
   
   // Scientific notation
   let largeNumber = 1e6;  // 1 million
   ```

2. **Strings**
   ```javascript
   let name = "Alice";
   let message = 'Hello, World!';
   
   // Template strings (modern JS)
   let greeting = `Hello, ${name}!`;
   
   // String operations
   console.log(name.length);  // 5
   console.log(name.toUpperCase());  // "ALICE"
   ```

3. **Booleans**
   ```javascript
   let isLoggedIn = true;
   let hasPermission = false;
   
   // Boolean operations
   let canAccess = isLoggedIn && hasPermission;
   ```

4. **undefined and null**
   ```javascript
   let notDefined;  // undefined
   let intentionallyEmpty = null;
   ```

#### Advanced Data Types (10 minutes)

1. **Symbol**
   ```javascript
   // Unique identifiers
   const id = Symbol('id');
   const anotherId = Symbol('id');
   console.log(id === anotherId);  // false
   ```

2. **BigInt**
   ```javascript
   // For really big numbers
   const bigNumber = 9007199254740991n;
   const result = bigNumber + 1n;
   ```

#### Data Structures (20 minutes)

1. **Arrays**
   ```javascript
   // Creating arrays
   let fruits = ['apple', 'banana', 'orange'];
   let numbers = [1, 2, 3, 4, 5];
   
   // Accessing elements
   console.log(fruits[0]);  // 'apple'
   
   // Array methods
   fruits.push('grape');  // Add to end
   fruits.pop();  // Remove from end
   fruits.unshift('kiwi');  // Add to start
   fruits.shift();  // Remove from start
   
   // Useful array operations
   let length = fruits.length;
   let includesBanana = fruits.includes('banana');
   
   // Array iteration
   fruits.forEach(fruit => console.log(fruit));
   ```

2. **Objects**
   ```javascript
   // Creating objects
   let person = {
       name: "Bob",
       age: 30,
       isStudent: false,
       hobbies: ['reading', 'gaming']
   };
   
   // Accessing object properties
   console.log(person.name);  // Dot notation
   console.log(person['age']);  // Bracket notation
   
   // Adding/modifying properties
   person.location = "New York";
   person.age = 31;
   ```

3. **Maps**
   ```javascript
   let userMap = new Map();
   
   // Setting values
   userMap.set('alice', { age: 25, role: 'admin' });
   userMap.set('bob', { age: 30, role: 'user' });
   
   // Getting values
   console.log(userMap.get('alice'));
   ```

4. **Sets**
   ```javascript
   let uniqueNumbers = new Set([1, 2, 2, 3, 3, 4]);
   console.log(uniqueNumbers);  // Set(4) {1, 2, 3, 4}
   
   uniqueNumbers.add(5);
   uniqueNumbers.delete(1);
   ```

#### Advanced Data Structure Operations (15 minutes)

1. **Array Methods Deep Dive**
   ```typescript
   interface Task {
       id: number;
       title: string;
       completed: boolean;
   }

   const tasks: Task[] = [
       { id: 1, title: 'Learn JS', completed: false },
       { id: 2, title: 'Build Project', completed: true },
       { id: 3, title: 'Write Tests', completed: false }
   ];

   // Map - transform each element
   const titles = tasks.map(task => task.title);

   // Filter - get subset of elements
   const incompleteTasks = tasks.filter(task => !task.completed);

   // Find - get first matching element
   const firstIncomplete = tasks.find(task => !task.completed);

   // Reduce - accumulate values
   const totalTasks = tasks.reduce((count, task) => count + 1, 0);

   // Sort - arrange elements
   const sortedTasks = [...tasks].sort((a, b) => a.id - b.id);

   // Some/Every - check conditions
   const hasCompletedTasks = tasks.some(task => task.completed);
   const allTasksComplete = tasks.every(task => task.completed);
   ```

2. **Object Operations**
   ```typescript
   interface Person {
       name: string;
       age: number;
       skills: string[];
   }

   // Object destructuring
   const person: Person = {
       name: 'Bob',
       age: 30,
       skills: ['JavaScript', 'TypeScript']
   };

   const { name, age } = person;

   // Spread operator
   const updatedPerson = {
       ...person,
       age: 31,
       location: 'New York'
   };

   // Object methods
   const keys = Object.keys(person);
   const values = Object.values(person);
   const entries = Object.entries(person);

   // Freezing objects
   const frozenPerson = Object.freeze(person);
   ```

#### Practical Example: Building a Library Management System (15 minutes)
```typescript
interface Book {
    id: string;
    title: string;
    author: string;
    available: boolean;
    borrower?: string;
}

class Library {
    private books: Map<string, Book> = new Map();
    private borrowHistory: Set<string> = new Set();

    addBook(title: string, author: string): void {
        const id = `book_${Date.now()}`;
        this.books.set(id, {
            id,
            title,
            author,
            available: true
        });
    }

    borrowBook(bookId: string, borrower: string): boolean {
        const book = this.books.get(bookId);
        
        if (!book || !book.available) {
            return false;
        }

        book.available = false;
        book.borrower = borrower;
        this.borrowHistory.add(borrower);
        this.books.set(bookId, book);
        
        return true;
    }

    returnBook(bookId: string): boolean {
        const book = this.books.get(bookId);
        
        if (!book || book.available) {
            return false;
        }

        book.available = true;
        book.borrower = undefined;
        this.books.set(bookId, book);
        
        return true;
    }

    searchBooks(query: string): Book[] {
        return Array.from(this.books.values()).filter(book => 
            book.title.toLowerCase().includes(query.toLowerCase()) ||
            book.author.toLowerCase().includes(query.toLowerCase())
        );
    }

    getBorrowers(): string[] {
        return Array.from(this.borrowHistory);
    }
}

// Usage example
const library = new Library();
library.addBook("The JavaScript Way", "John Doe");
library.addBook("TypeScript in Action", "Jane Smith");
```

### Exercise: Enhanced Contact Manager
Build a contact management system that:
1. Uses TypeScript interfaces
2. Implements CRUD operations
3. Includes search functionality
4. Validates phone numbers and emails
5. Prevents duplicates
6. Maintains a history of changes

### Next Lesson Preview
In our next lesson, we'll learn about algorithms and how to use these JavaScript fundamentals to solve real problems!
