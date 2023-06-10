# Game Code

This repository contains code for a simple game implemented using TypeScript and the RxJS library. The game involves controlling a frog and avoiding cars and logs to reach the goal.

## Getting Started

To run the game, follow these steps:

1. Clone the repository: `git clone <repository_url>`
2. Install the dependencies: `npm install`
3. Build the TypeScript code: `npm run build`
4. Open the html file dist/index.html (NOT src/index.html)

## Gameplay

- Use the arrow keys (ArrowLeft, ArrowRight, ArrowUp, ArrowDown) or WASD keys to move the frog.
- Avoid colliding with cars and logs.
- Reach the goal area to increase your score.
- If you collide with a car or fall into the river, the game is over.

## Dependencies

The following dependencies are required to run the game:

- RxJS: Reactive Extensions library for JavaScript.

## Code Structure

The code is structured as follows:

- The `main` function initializes the game and sets up the event observables.
- The `keyObservable` function creates an observable for a specific key event.
- The `createCar` and `createLog` functions create car and log objects respectively.
- The `createFrog` function creates the frog object.
- The `moveBody` function moves a body object based on its direction and speed.
- The `handleCollissions` function checks for collisions between bodies and updates the game state accordingly.
- The `tick` function updates the game state on each tick of the game loop.
- The `reduceState` function reduces the game state based on the input event.

## Contributing

Contributions to the project are welcome. If you find any issues or want to add new features, feel free to open an issue or submit a pull request.

# Functional Programming Concepts

1. **Immutability**: The code heavily relies on immutability, where objects are not modified directly but new objects are created instead. This is evident throughout the code, such as when creating new instances of `Body` objects or updating the state in the `handleCollisions` function. Immutability ensures that data remains unchanged, reducing complexity and potential side effects.

2. **Pure Functions**: Functions in the code are designed to be pure functions, which means they produce the same output for the same inputs and have no side effects. Functions like `moveBody`, `bodiesCollided`, `addSpeed`, and `handleCollisions` take input parameters and return a new value without modifying any external state. Pure functions make code more predictable, testable, and easier to reason about.

3. **Higher-order Functions**: The code utilizes higher-order functions, which are functions that take one or more functions as arguments or return another function. For example, the `keyObservable` function is a higher-order function that takes an event name, key name, and a result function and returns an observable. This promotes modularity and reusability by abstracting away common behavior and allowing for composition of functions.

4. **Function Composition**: The code uses function composition, where multiple functions are combined to form a new function. This can be observed in the `tick` function, which combines the `handleCollisions` and `map` functions to transform the state. Function composition allows for a more declarative style and simplifies complex transformations.

5. **Higher-order Observables**: The code leverages the `rxjs` library, which provides functional reactive programming capabilities through observables. Observables are streams of values that can be transformed using various operators. The code utilizes higher-order observables such as `filter`, `map`, and `scan` to filter, transform, and accumulate values emitted by the observables. This enables handling of asynchronous events in a functional and declarative manner.

Functional programming promotes modularity, reusability, and maintainability by focusing on pure functions, immutability, and function composition. It helps reduce complexity, improve code quality, and make programs more concise and readable.
