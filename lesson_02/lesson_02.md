## Lesson 02

### Boolean Algebra and Logic - The Mathematics of Computing

#### Intro
- Start with a thought experiment: "Imagine you're at a restaurant trying to decide what to order. The menu says 'If you order a main course AND a drink, OR if you're a member, you get free dessert.' How do we break this down into simple yes/no decisions?"
- Last time, we learned that computers speak in binary - 1s and 0s. Today, we'll learn about how these simple 1s and 0s can be used to make complex decisions through something called Boolean algebra.

#### George Boole
- George Boole's story is one of the most remarkable in mathematics history. Born in 1815 in Lincoln, England, to a working-class family, his father was a shoemaker with a passionate interest in mathematics and scientific instruments. Despite having no formal education beyond elementary school, young George taught himself mathematics, Latin, and Greek. By age 16, he was teaching at a local school to support his family, spending every free moment studying mathematics journals at the local library.
- What made Boole extraordinary was his ability to see connections that others missed. While teaching and studying, he began developing new ideas about logic and mathematics. He realized that logical reasoning could be reduced to a kind of algebra, where statements could be either true or false, just as numbers could be positive or negative. This was revolutionary – before Boole, logic was seen as part of philosophy, not mathematics.
- In 1847, he published "The Mathematical Analysis of Logic," which introduced his algebraic approach to logic. This was followed by his masterpiece "An Investigation of the Laws of Thought" in 1854. In these works, he showed how logical reasoning could be reduced to simple mathematical operations, introducing what we now call Boolean algebra. Despite facing initial skepticism from some mathematicians, he was awarded the Royal Society's Royal Medal in 1844 and was appointed as the first professor of mathematics at Queen's College, Cork (now University College Cork) in Ireland.
- Perhaps the most fascinating aspect of Boole's work is that its true importance wasn't realized until long after his death in 1864. It wasn't until the 1930s when Claude Shannon, while working on his master's thesis at MIT, recognized that Boolean algebra could be used to design electrical circuits. This revelation became one of the foundational principles of modern computing, making Boole's work from the 1850s the mathematical backbone of every computer and digital device we use today.

#### Basic Boolean Operations
- There are 3 basic operations in Boolean algebra: AND, OR, and NOT. These operations are used to combine simple true/false statements into more complex logical expressions.
- A truth table is a systematic way to show all possible combinations of inputs and their corresponding outputs in logical operations. Think of it as a complete catalog of "what if" scenarios for any logical statement.

#### NOT
- The simplest truth table: NOT operation
- The NOT operation is used to negate a condition. It returns true if the condition is false, and vice versa.
- Example: I am NOT hungry.
- Truth table for NOT:

Input (A) | Output (NOT A)
---------|-------------
   0     |     1
   1     |     0

This shows both possible scenarios for a single input

##### AND
- The AND operation is used to combine two or more conditions. It returns true only if all the conditions are true.
- Example: That dog is small AND cute.
- Truth table for AND:

A | B | A AND B
--|---|--------
0 | 0 |   0
0 | 1 |   0
1 | 0 |   0
1 | 1 |   1

##### OR
- The OR operation is used to combine two or more conditions. It returns true if at least one of the conditions is true.
- Example: I'll have tea OR coffee.
- Truth table for OR:

A | B | A OR B
--|---|--------
0 | 0 |   0
0 | 1 |   1
1 | 0 |   1
1 | 1 |   1

#### Combining Operations
- We can combine these basic operations to create complex logical expressions.
- Example: A file can be opened if the user is an admin OR (the user is the file owner AND the file is not locked).
- Truth table for the example:

A | O | L | NOT L | O AND (NOT L)
--|---|---|-------|--------------
0 | 0 | 0 |   1   |       0
0 | 0 | 1 |   0   |       0
0 | 1 | 0 |   1   |       1
0 | 1 | 1 |   0   |       0
1 | 0 | 0 |   1   |       0
1 | 0 | 1 |   0   |       0
1 | 1 | 0 |   1   |       1
1 | 1 | 1 |   0   |       0

### Why Boolean Algebra Matters in Computing
- Remember those transistors we talked about last time? They implement Boolean logic!
- Each transistor can be thought of as a tiny Boolean logic gate
- Complex computer operations are built from combinations of these simple gates

#### Real World Example
IF (app_has_permission AND notification_enabled) AND
   (is_important OR user_requested)
THEN show_notification

### Practical Application

#### Smart Home System
- Design the logic for a smart light that turns on if
  - It's dark outside AND motion is detected, OR
  - The manual switch is pressed"

JS CODE:
```javascript
const isDarkOutside = true;
const motionDetected = true;
const manualSwitchPressed = false;

if ((isDarkOutside && motionDetected) || manualSwitchPressed) {
  console.log("Turn on the light");
} else {
  console.log("Keep the light off");
}
```

#### Social Media Filter
- How would you write the logic for a social media filter that shows posts if:
  - They're from your friends AND less than 24 hours old, OR
  - They're marked as important, OR
  - They mention you

#### Traffic Light Logic
- How would you write the logic for a traffic light that:
  - Turns green if the pedestrian light is red AND the traffic light is green
  - Turns red if the pedestrian light is green OR the traffic light is red

#### Elevator Logic
- How would you write the logic for an elevator that:
  - Moves up if the requested floor is above the current floor
  - Moves down if the requested floor is below the current floor
  - Stops if the requested floor is the current floor

### Conclusion
- Boolean algebra is the mathematics of yes/no decisions
- Complex decisions can be broken down into combinations of AND, OR, and NOT
- This forms the foundation of how computers "think"
- Next time, we'll look at how we can use these logical building blocks to create more complex operations in computers.
