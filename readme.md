# MAD - Exercise 01
## Tasks
* Watch the Kotlin Crashcourse Video in Moodle or complete the tutorials **[Introduction to programming in Kotlin](https://developer.android.com/courses/pathways/android-basics-compose-unit-1-pathway-1)** and **[Kotlin fundamentals](https://developer.android.com/courses/pathways/android-basics-compose-unit-2-pathway-1
)**.
* Answer the questions inside this Readme.md file and push it to your repository.
* Submit your coding solution of the Number Guessing Game inside the repository.
* Submit the link to your repository in Moodle.

## Questions
### Describe how Kotlin handles null safety. What are nullable types and non-null types in Kotlin? (0,5 points)

<span style="color:blue">Provide your answer here! </span>

<span style="color:yellow">Kotlin is designed in a way to remove the risk of null-references. We differ between "Non-Nullable-Types" and "Nullable-Types". </span>

<span style="color:yellow">Non-Nullable-Types in Kotlin are types that can <a style="color:red"> NOT </a> be set to null. If tried, the compiler would give out an error. In 
example 1) in the code snippet, we can see that the null safety is given with 
a normal var declaration. If we wanted to "enable" a var to be null, we would have to use "?" as in 2) shown.</span>

<span style="color:yellow">Nullable-Types in Kotlin are types that can be set to null. This can be set by adding a "?" to the type. In the code snippet 2) down below is an example  </span>
> Note: you can also use code snippets to illustrate your answer. 

```kotlin 
// 1) Non-Nullable Types
var a: String = "Non-Nullable-Type"  // normal declaration 
a = null // can NOT be done because no null type allowed

// 2) Nullable-Types
var b: String? = "Nullable-Type"  //define Nullable type with "?"
b = null  // can be done because we "allowed" it
```

### What are lambda expressions and higher order functions in Kotlin? Why would you store a function inside a variable? (0,5 points)

<span style="color:blue">Provide your answer here!</span>

<span style="color:yellow">In Kotlin, a lambda expression is a function that is not declared and thus has no name. It's surrounded by Curly braces {}. The return value is the last expression inside the body,
which comes after the "->" arrow. The Syntax for a lambda expression is <a style="color:pink"> {parameters -> body}</a>. One simple example in 1).</span>

<span style="color:yellow">A Higher-Order-Function is a function which takes functions as parameters or returns a function. </span>

<span style="color:yellow">Storing a function in a variable can be useful because it enables the functionality to pass a function as a parameter to another function. Thus, we don't have to redefine it every time. </span>

<span style="color:yellow">Code snippet example:</span>

```kotlin 
// 1) a simple lambda expression which calculates the sum of two numbers
val sum: (Int, Int) -> Int = { a: Int, b: Int -> a + b }
```

### Provide a solution for the following number guessing game inside `App.kt`. (3 points)

## Number Guessing Game in Kotlin
The game is a simple number guessing game. The task is to generate a random, max 9-digit, number. The number must **not contain repeating digits**. Valid digits are 1-9.
Ask the user to guess the max 9-digit number. The game is finished when the user guesses the correct digits in the correct order.
In each round, the user gets feedback about the number of correct digits and the number of correct digits in the correct position.
The output should be in the format "n:m", where "n" is the number of digits guessed correctly regardless of their position, 
and "m" is the number of digits guessed correctly at their correct position. Here are some examples:

This example shows the game flow with 4-digits to guess (the default argument)

Generated number: 8576
-	User input: 1234, Output: 0:0
-	User input: 5678, Output: 4:1
-	User input: 5555, Output: 1:1
-	User input: 3586, Output: 3:2
-	User input: 8576, Output: 4:4 -> user wins

Take a look into the provided code structure in `src/main/kotlin/App.kt`. Implement the following methods (lambda expressions):
- _playNumberGame(digitsToGuess: Int = 4)_ (1 point): The main game loop that handles user input and game state. Make use of _generateRandomNonRepeatingNumber_ and _checkUserInputAgainstGeneratedNumber_ here. This function also utilizes a default argument 
- _generateRandomNonRepeatingNumber_ (1 point): A lambda expression that generates a random number with non-repeating digits of a specified length.
- _checkUserInputAgainstGeneratedNumber_ (1 point): A lambda expression that compares the user's input against the generated number and provides feedback.

``CompareResult.kt`` This class is a data structure which helps with bundling the result of the comparison of the user input and the generated number. Look at the toSting() and use it in your output.

Run the project with `./gradlew run` and test your implementation with the provided tests in `src/test/kotlin/AppTest.kt` with `./gradlew test`.

# Project Structure
The project is structured into two main Kotlin files:

**App.kt**: Contains the main game logic and functions.

**AppTest.kt**: Contains unit tests for the various functions in App.kt.

