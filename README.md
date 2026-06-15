## important links:

[source repo](https://github.com/FullstackAcademy/tdd-loops.git)

---

# Loops Intro

## Instructions

1. Choose one person in your group to share their screen. They will be in charge of typing
   your answers.
2. Select another person in the group to be responsible for sharing your answers with
   the class later on.
3. As a team, read each question out loud and reach a consensus on the answer before
   moving to the next question.

## Reassign variable values

Evaluate the following snippets of code _manually_ without using the browser console.

```js
let x = 1;
let y = 2;
y = x;
x = y;
```

1. What are the initial values of `x` and `y`?
2. What are the final values of `x` and `y`?
3. Why is the final value of `x` _not_ 2?

```js
let x = 1;
let y = 2;

let z = y;
y = x;
x = z;
```

4. What are the initial values of `x` and `y`?
5. What are the final values of `x` and `y`?
6. What is the purpose of `z`?

```js
let x = 1;
x = x + 1;
x += 1;
x++;
x *= 2;
x -= 3;
```

`x = x + 1`, which is read as "Assign the _value_ `x+1` to the _variable_ `x`", is such
a common operation that there is **syntactic sugar** for it.

`x += n` is shorthand for `x = x + n`. This works for other basic arithmetic operations as well!

`x++` and `x--` are special shorthands for `x+=1` and `x-=1` respectively.

7. What is the difference between a variable and a value?
8. What is the initial value of `x`?
9. What is the final value of `x`?

## Read looping code

A **while loop** repeats the code in its **body** _while_ its **condition** evaluates to `true`.
When the condition evaluates to `false`, the code immediately continues to the line
after the body.

The code snippet below uses a loop to simulate flipping a coin.

```js
let heads = true;
while (heads) {
  if (Math.random() < 0.7) {
    console.log("Heads!");
  } else {
    heads = false;
  }
}
console.log("Tails :(");
```

10. `Math.random()` returns a uniformly random floating-point number from 0 (inclusive)
    to 1 (exclusive). Does the code above simulate a fair coin?
11. Is it possible to know how many times the loop will execute _before_ running the code?
    Why or why not?
12. In words, describe when the loop will stop.

```js
let i = 0;
while (i < 3) {
  console.log(i);
  i += 1;
}
console.log("Done!");
```

13. Will the snippet above print the number 3? Why or why not?
14. How many times does this loop run? Explain your reasoning.
15. Suppose the order of the code in the body were reversed, so `i += 1` happens _before_
    `console.log(i)`.
    1. Does this change what the snippet prints?
    2. Does this change the number of times the loop runs?
16. What are 3 different ways to modify the code so that the loop only executes _twice_?

```js
let i = 0;
while (i < 3) {
  console.log("Loading...");
}
console.log("Done!");
```

17. What would happen if we ran this snippet of code?
18. Why might we consider this an error, even if an error message is not displayed?
19. How would we fix this error so "Loading..." only gets printed 3 times?

```js
for (let i = 5; i > 0; i--) {
  console.log(i);
}
console.log("Done!");
```

20. A **for loop** is syntactic sugar for a while loop. Translate the snippet above
    back into a while loop.
21. Will the snippet above print the number 0? Why or why not?

```js
function factorial(n) {
  let result = 1;
  for (let i = 1; i <= n; i++) {
    result *= i;
  }
  return result;
}
```

The factorial of a non-negative integer `n` is defined as the product of all
positive integers less than or equal to `n`. For example, $3! = 3 * 2 * 1 = 6$.
This snippet demonstrates a very common technique: using a loop to modify
the value of some variable.

22. Why is `result` in scope in the body of the for loop?
23. How is `i` used to control the number of times the loop runs?
24. How is `i` used to modify the value of `result`?
25. What does `factorial(0)` return?

> [!TIP]
>
> The name of your loop variable doesn't have to be `i`!
> You can name it whatever you want, but `i` is the convention that
> many software engineers default to. You can think of it as
> "i" for "iterate".
