# Strings (Music) Theory

[![Run on Repl.it](https://repl.it/badge/github/upperlinecode/string-theory-javascript-methods)](https://repl.it/github/upperlinecode/string-theory-javascript-methods)

## The Goal

Musicians love to take vocals and modulate them or otherwise mess with them. Missy Elliott put her thing down, flipped it, and reversed it. T-Pain autotuned an entire decade. Kanye will muffle loud yells so they sound distant, and Bon Iver will take near-whispers and turn them into a wall of sound and emotion.

![beatmapper](https://media.giphy.com/media/10ZQLUWJ4HwvS/giphy.gif)

What they can do to voices with vocoders, autotuners, and sequencers, we can do to written words.

## Printing v. Returning

It can be really tempting to get into the habit of printing, usually with code like this:

```javascript
const name = "Sarah"
console.log(name)
```

That's fine for now, because until we start piping data to websites, there's nowhere else for it to go. Printing it to the console with a `console.log` statement is the only way we can see what we are doing and whether or not it's working.

#### The problem with `console.log()`

The trouble with printing to the console is that if you think about the way you use any technology, you probably don't use a console much at all outside of this class. If you showed your friends the console without explaining it, they'd probably have no clue how to work it!

![console2k17](https://media.giphy.com/media/yR4xZagT71AAM/giphy.gif)

When you print something to the console, it's gone. You can't use it unless you access the data again. But for a lot of what we do in programming, we need to save information. So while printing information helps us understand our code and see if it's running correctly, returning is far more helpful in building more powerful programs.

#### Using both!

One of the best ways to use `console.log()` is to check and see whether what you think is happening is really happening. If it isn't there, then you can narrow down what part of your program has broken down.

Consider this example of a function called "double", which takes in an integer and returns double that integer.

```javascript
function double(someNumber) {
    console.log("Currently attempting to double the number " + someNumber.toString())
    const theAnswer = someNumber * 2
    return theAnswer
}
```

If you run that code without calling the function, nothing at all will print out.

Instead, you'd need to also test it out with a specific number by *calling* the function:

```javascript
function double(someNumber) {
    console.log("Currently attempting to double the number " + someNumber.toString())
    const theAnswer = someNumber * 2
    return theAnswer
}

double(7)
```

If you run that code, you'll probably see code that confirms that it's running, but you won't see the actual answer, which is 14.

To see *that* you'd need to print whatever the return value is for the function as it is called:

```javascript
console.log(double(7)) // this will PRINT OUT the return value of the function we just wrote.
```

This will print out TWO things:
1. Our debugging statement (the console.log() from inside of our function), because that happens when the function is running.
2. The return value, because we told it to print whatever double(7) returns.

Since double(7) returns 14, that means anywhere we type double(7), we can think of it as the exact same thing as 14, and we can use it in the same way we would use the number 14. Think about how much more we can do with this!

```javascript
// We can store the answer in a variable x to use later.
const x = double(7)

// We can use it as a test for an if statement
if (double(7) == 2 * (3 + 4)) { // Both the left and right should return the number 14
  console.log("Good, our math works.")
}

// We even use it to store and respond to user input
const age = parseInt(prompt())
console.log("Wow!, you're halfway to " + double(age).toString() + "!")
```

Remember: by coding return values into our functions, you won't *see* the return if you only call the functions. That means that if you write a function called "myCoolFunction" that returns a string, then you'll need to explicitly tell it to "console.log(myCoolFunction())" if you also want that string printed out.
