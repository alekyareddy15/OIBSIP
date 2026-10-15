# Number Guessing Game

A console game written in core Java. The computer picks a random number and you guess it, getting "Too High!" or "Too Low!" hints until you win or run out of attempts.

Built for Oasis Infobyte SIP, Java Development track, Task 2.

## Features

- Random number generated at the start of every round
- Hints after each guess: `Too High!`, `Too Low!` or `Correct!`
- Attempt counter shown on every prompt (for example `Attempt 3/7`)
- Maximum attempts per round. If you run out, the game says `You Lost!` and reveals the number
- Play Again option after each round
- Scoreboard across rounds, such as `Round 1 - guessed in 4 attempts [Medium]`
- Three difficulty levels
- Input validation: letters and out-of-range numbers are rejected and you are asked again

## Difficulty levels

| Level  | Number range | Attempts |
|--------|--------------|----------|
| Easy   | 1 to 50      | 10       |
| Medium | 1 to 100     | 7        |
| Hard   | 1 to 200     | 5        |

## How to run

You need JDK 17 or later.

```
javac NumberGuessingGame.java
java NumberGuessingGame
```

## How it works

- `Difficulty` is an enum that holds the label, the highest number and the attempt limit for each level.
- `RoundResult` stores the outcome of one round (won or lost, attempts used, the secret number) so the scoreboard can be printed at any time.
- `playRound` generates the secret number with `java.util.Random` and loops until the player guesses it or the attempts run out.
- `readInt` keeps asking until the player types a valid number inside the allowed range.
- All rounds are kept in an `ArrayList<RoundResult>`, which is printed after every round and again when the player quits.

## Screenshots

| Winning a round | Losing a round | Scoreboard |
|---|---|---|
| ![win](screenshots/win.png) | ![lose](screenshots/lose.png) | ![scoreboard](screenshots/scoreboard.png) |
