## Writing Cleaner Code


### 1. Use clear, desciptive names for functions and variables
Comments are all well and good, but part of writing clean code is writing in a way that another developer can easily come behind you 
and tell what the code does by looking at it. Your comments should serve to provide clarification, but ideally your code will be readable without comments. To this end, you should choose names that 
are descriptive and clearly communicate your intent. For example, a variable that stores a user's age:

```js
// bad
const x

// good
const age

// better
const userAge

/* note: the above might not be the case depending on where this variable is stored; for exampler, if it's contained in a 'user' object, then user.age would be very clear and user.userAge would be redundant. */
```

### 2. Shorten your functions 
This is, from my experience, an indicator of the experience level of the developer writing the code. When I first started coding, I put everything into long functions; it was easier for me to understand all the steps that were taking place this way. As you become more experienced, you will beging to realize that there are a number of benefits to separating your code into smaller functions that each handle only one task. The benefits of smaller functions include:
- easier to test
- easier to refactor
- easier to see what each individual function is doing
- less redundancy

Code that is made up of more and shorter functions isn't necessarily easier to write, but it is far, far easier to make adjustments to and makes for a much smoother handoff to other developers.


### 3. Use a consistent style
Consistent style choices go a long way toward making code readable. If you are part of a larger development team, this is all the more important.
My goal in contributing to a team's codebase is to make it hard to tell who wrote a particular line of code without checking the git blame.
Using tools like ESLint and Prettier will go a long way toward making this happen; in fact, if there's one tip I would give to new developers that will
make a huge difference, it's to start using those tools. They make front-end development so much faster and easier, and make youi a better developer for using them.

### 4. Don't repeat yourself
Often referred to as the DRY principle or DRY programming, this is a natural result of breaking code into smaller functions. Smaller functions that do one thing well can then be reused. Any time you see yourself doing the same thing two or three times, you can take that as an indicator that that functionality should be separated out into its own function.

### 5. Write a lot of code, then refactor it.
Like many skills, part of becoming a better programmer is simply spending time at it. There is no better way to learn than to build stuff.
I've found it's a far more effective approach than following step-by-step tutorials. Repetition alone won't make your code better, though. Yes,
you need to put in time and lines of code- but going over that same code with a critical eye and refactoring, especially with input from more senior developers,
is equally as important. Practicing the wrong way of doing something over and over won't make you do it right- you need to correct your mistakes,
improve your form, and continue using what you've learned. I've heard it said this way- a developer could have get 5 years of experience under their belt, but
not have progressed very far because it's the same year repeated five times. Practice doesn't make perfect- perfect practice makes perfect. So write a bunch of code, then go back and make it better!
