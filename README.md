# Burger Place
**Burger Place** is a design concept for an esoteric programming language that has a wordy syntax based on fast food restaurants and confusing semantics. Design concept and all examples are available for free of charge.

1. All data is made of stacks, which stores numbers and other stacks. The dish infers to the value you currently working on (accumulator). The term, top of, infers the last item of a stack, and calling them is recursive.

2. Customers are used to generate inputs and receive outputs so it can be logged to the console. The amount of times the order can be generated can be randomized. You can still display information without the need of costumers, but it can only be numbers.

3. The fridge, which you store data, stores a limited number of “boxes” and these boxes cannot be named.

4. In order to run a program, you write `lunchtime!` at the end of the program. Everything after it is ignored.

5. Code blocks are tab indented.

6. Brackets are used to write comments.

## Commands
Here's a list to every command available in Burger Place. Ones in *italic* are code blocks. Each command can only be used in their respective category. 

### Order Commands
| Command      | Information |
| ------------ | ----------- |
| *`orders for A to B`* | Generates orders (inputs). Repeats for a random number (between **A** and **B**) of times. |
| *`i'll take`* | Creates a customer and a stack to work with. |
| `a number A` | Adds **A** at the end of the current stack. |
| `A number Bs` | Adds **B** to the current stack by **A** times. |
| `should i get a A or a B?`, `should i get an A or an B?` | Adds a random number (between **A** and **B**) to the current stack. |
| *`a meal of`* | Adds a substack to the current stack. |
| `that would be?` | Asks the user for some input. The answer gets converted into a number, then it adds said number to the current stack. | 
| `what again?` | Asks the user for some input. Each character is converted into numbers, then it adds a substack to current stack out of said numbers. |
| `that would be a A?`, `that would be an A?` | Adds a substack to current stack out of numbers based from **A**. |

### Fridge Commands
| Command      | Information |
| ------------ | ----------- |
| *`fridge of A`* | Generates boxes (memory / data), which amount is determed by **A** (1 to **A**). |
| `there's a A`, `there's an A` | Updates the first empty box with **A**. |
| `there's A Bs` | Updates multiple empty boxes (amount determed by **A**) with **B**. |
| *`there's a bag of`* | Updates the first empty box with a stack. Useable within stacks. |

### Kitchen Commands
| Command      | Information |
| ------------ | ----------- |
| *`in the kitchen`* | The "program" part, manages inputs and boxes to create outputs. |
| `prepare order` | Loads the first available input. |
| `it's ready!` | Outputs the dish. The value of it resets afterwards. |
| `lunch break!` | Directly outputs the dish. Does not serve dish to costumers, and can only be numbers. |
| `throw away the dish` | Resets the value of the dish. |
| `take A from the fridge` | Overwrites the value of the dish with box #**A**. |
| `store the dish in the fridge at A` | Overwrites the value of box #**A** with the dish. |
| `looking at the top of A, take from the fridge` | Uses the top of box #**A** to access another box, then overwrites the dish's value. For example, if the top of box #1 is 3, the dish would be the value of box #3. |
| `looking at the top of A, store it in the fridge` | Uses the top of box #**A** to access another box, then overwrites it with the dish's value. |
| `add A from the fridge with the dish` | Overwrites the dish with the sum of the top of itself with the top of box #**A**. |
| `looking at the top of A, add with the dish` | References a box with the top of box #**A**, then overwrites the dish with the sum of the top of itself with the top of referenced box. |
| `with A from the fridge, rip into the dish` | Overwrites the dish with the difference of the top of itself with the top of box #**A**. |
| `looking at the top of A, rip into the dish` | References a box with the top of box #**A**, then overwrites the dish with the difference of the top of itself with the top of referenced box. |
| `add some pepper onto the dish` | Increments the top of the dish by one, then updates the dish's value. |
| `add some salt onto the dish` | Decrements the top of the dish by one, then updates the dish's value. |
| `add some pepper to A from the fridge` | Increments the top of box #**A** by one, then updates both the box's and the dish's value with the new value. |
| `add some salt to A from the fridge` | Decrements the top of box #**A** by one, then updates both the box's and the dish's value with the new value. |
| `looking at the top of A, add some pepper` | Referencing a box with the top of box #**A**, increment its top by one, then updates both the box's and the dish's value with the new value. |
| `looking at the top of A, add some salt` | Referencing a box with the top of box #**A**, decrement its top by one, then updates both the box's and the dish's value with the new value. |
| `stack the dish onto A` | Stacks a copy of the dish's value at the top of box #**A**, then updates the box's value. |
| `looking at the top of A, stack onto the dish` | Referencing a box with the top of box #**A**, stacks a copy of the dish's value on the top, then updating the box's value. |
| `take from A, and stack onto the dish` | Takes the last item of box #**A**, and stacks it on the top of the dish. Updates both the box's and the dish's values. |
| `looking at the top of A, take and stack onto the dish` | Referencing a box with the top of box #**A**, take the last item of that box, and stacks it on the top of the dish. Updates both the box's and the dish's values. |

#### Conditional Statements
Condtional statements checks the value of the top of the dish, and runs selections of code if its condition is met. A conditional statement is a code block that supports an else statement, looping, and breaks and continues.

| Condition    | Information |
| ------------ | ----------- |
| `always` | Always met |
| `is the dish missing?` | Has no value |
| `is there a dish?` | Has a value |
| `is the dish overcooked?` | Is a positive number and not zero |
| `is the dish undercooked?` | Is a negative number and not zero |
| `is the dish cooked just right?` | Is zero |
| `does the dish need more work?` | Is not zero |

| Command      | Information |
| ------------ | ----------- |
| *`not the case?`* | Runs if the condtion was not met. If the statement loops, run once then continue on the program. |
| `check again` | Repeats conditional statement if the condition was met. |
| `step back A times` | Breaks out of statements by **A** times. Does not loop current statement. |
| `step back A times, check again` | Breaks out of statements by **A** times, then loops current statement. |

### Dining Room Commands
| Command      | Information |
| ------------ | ----------- |
| *`in the dining room`* | Uses generated outputs to display information back the user. |
| `after some chit chat` | Repeats dining room code if there's any customer left that didn't get any outputs. |
| `a customer gets his and drinks first`, `a customer gets hers and drinks first`, `a costumer gets theirs and drinks first` | Outputs the first available output. |
| `a customer gets A and drinks first` | Outputs output #**A**. |
| `a customer gets his and eats it`, `a customer gets hers and eats it`, `a costumer gets theirs and eats it` | Outputs the first available output converted into a string of characters. |
| `a customer gets A and eats it` | Outputs output #**A** converted into a string of characters. |
