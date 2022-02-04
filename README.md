# Bamboo Forest Time Gate Puzzle

## The main idea
Inspired by the movie Shang-Chi is the mythical village of Ta Lo, protected by a sentient and moving Bamboo Forest that opens every 15 years.

The outer puzzle is time locked to only be accessible at some interval (e.g. every 10,000 blocks since creation) and only for N consecutive blocks upon which the outer puzzle is again locked.

Solutions reveal a series of inner puzzles (that are actual puzzles) with feedback given via exception raise messages.

Inner puzzles are curried as to not be identical every interval (though revealed puzzle would show the mechanisms for determining the solution anyway).

At the end of the puzzle chain is a wallet with a reward.

### What was implemented
A single puzzle that's a simplified version of Wordle -- guessing a 5 letter word with raise exception letting you know if a letter in a particular spot is exactly correct. As feedback is given on unsuccessful spends, the mechanism to prevent a brute force approach is really the limited time window for which the time lock requirement is met. 

Unrevealed inner puzzles would prevent any brute force approach from being coded ahead of time. But over iterations of the game (every 10000 blocks), one would expect to get closer and closer as the outer puzzles will be "solved".

### Big missing pieces
- Currying
- Separating out the single puzzle into a series of inner puzzles
- Better sig checks to prevent common attacks

## Acknowledgements
Thank you to the Clovyr team for a great platform to develop on. Definitely streamlined the onboarding to get coding right away with 24 hours.

Thank you to the Chia team for creating awesome searchable docs and videos. And thank you for the live support.
