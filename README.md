## important links:

[source repo](https://github.com/FullstackAcademy/loops-intro.git)

---

# Loops Intro

## Instructions

1. Choose one person in your group to share their screen. They will be in charge of typing
   your answers.
3. Select another person in the group to be responsible for sharing your answers with
   the class later on.
4. As a team, read each question out loud and reach a consensus on the answer before
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
    * answer: x = 1 | y = 2
2. What are the final values of `x` and `y`?
    * answer: x = 1 | y = 1
3. Why is the final value of `x` _not_ 2?
    * answer: because y is set to 1 before x is set to y

```js
let x = 1;
let y = 2;

let z = y;
y = x;
x = z;
```

4. What are the initial values of `x` and `y`?
    * answer: x = 1 | y = 2
5. What are the final values of `x` and `y`?
    * answer: x = 2 | y = 1
6. What is the purpose of `z`?
    * answer: placeholder for original value of y

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
    * answer: a value is a bit of data stored by a variable
8. What is the initial value of `x`?
    * answer: x = 1
9. What is the final value of `x`?
    * answer: x = 5

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
    * answer: no
11. Is it possible to know how many times the loop will execute _before_ running the code?
    Why or why not?
    * answer: no, because the loop only ends when a random value occurs
12. In words, describe when the loop will stop.
    * answer: The loop stops when the heads variable becomes false; which only happens when a random number is generated larger than 0.7

```js
let i = 0;
while (i < 3) {
  console.log(i);
  i += 1;
}
console.log("Done!");
```

13. Will the snippet above print the number 3? Why or why not?
    * answer: no, i only becomes 3 at the very end of the while loop and doesn't get printed to console
14. How many times does this loop run? Explain your reasoning.
    * answer: 3 times, you start at 0 and loop to 3
15. Suppose the order of the code in the body were reversed, so `i += 1` happens _before_
    `console.log(i)`.
    1. Does this change what the snippet prints?
        * answer: yes
    2. Does this change the number of times the loop runs?
        * answer: no
16. What are 3 different ways to modify the code so that the loop only executes _twice_?
    1. change the conditional to (i<2))
    2. change the declaration to i=1
    3.  change the declaration to i=2 and the contion to (i<4)

```js
let i = 0;
while (i < 3) {
  console.log("Loading...");
}
console.log("Done!");
```

17. What would happen if we ran this snippet of code?
    * answer: "loading..." will be printed to console infinitely
18. Why might we consider this an error, even if an error message is not displayed?
    * answer: We probably want the while loop to end after 3 loops; infinite loops aren't good to leave running forever
19. How would we fix this error so "Loading..." only gets printed 3 times?
    * answer: add an increment (i++;) to the while loop

```js
for (let i = 5; i > 0; i--) {
  console.log(i);
}
console.log("Done!");
```

20. A **for loop** is syntactic sugar for a while loop. Translate the snippet above
    back into a while loop.
    * ```js
      let i = 5;
      while (i > 0) {
         console.log(i);
         i--;
      }
      console.log("Done!");
      ```
21. Will the snippet above print the number 0? Why or why not?
    * answer: no, the loop ends before 0 can be printed

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
    * answer: because it is defined inside the same function as the for loop
23. How is `i` used to control the number of times the loop runs?
    * answer: i starts at 1 and increases by 1 for each loop until i is equal to n
24. How is `i` used to modify the value of `result`?
    * answer: each loop result is multiplied by i
25. What does `factorial(0)` return?
    * answer: 1

> [!TIP]
>
> The name of your loop variable doesn't have to be `i`!
> You can name it whatever you want, but `i` is the convention that
> many software engineers default to. You can think of it as
> "i" for "iterate".
