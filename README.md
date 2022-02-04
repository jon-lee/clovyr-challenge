# Bamboo Forest Time Gate Puzzle

## The main idea
Inspired by the movie Shang-Chi is the mythical village of Ta Lo, protected by a sentient and moving Bamboo Forest that opens every 15 years.

The outer puzzle is time locked to only be accessible at some interval (e.g. every 10,000 blocks since creation) and only for N consecutive blocks upon which the outer puzzle is again locked.

Solutions reveal a series of inner puzzles (that are actual puzzles) with feedback given via exception raise messages.

Inner puzzles are curried as to not be identical every interval (though revealed puzzle would show the mechanisms for determining the solution anyway).

This is really meant to take advantage of the fact that puzzles are not revealed until spent, creating a sequence of unknown "next challenges" where the limitation for solving is the limited timebound upon which valid spends can be performed. Outside of this interval, there's no way to gleam any information about further inner puzzles as even the first timebound condition can no longer be met. Upon failing to solve within that time interval, the coin can recreate itself to reset the relative timelocks and presumably users will have an easier time solving it the next time the game is open due to any knowledge gained from the first iteration.

At the end of the puzzle chain is a wallet with a reward.

### What was implemented
A single puzzle that's a simplified version of Wordle -- guessing a 5 letter word with raise exception letting you know if a letter in a particular spot is exactly correct. As feedback is given on unsuccessful spends, the mechanism to prevent a brute force approach is really the limited time window for which the time lock requirement is met. 

Unrevealed inner puzzles would prevent any brute force approach from being coded ahead of time. But over iterations of the game (every 10000 blocks), one would expect to get closer and closer as the outer puzzles will be "solved".

### Big missing pieces
- Time lock
- Currying
- Separating out the single puzzle into a series of inner puzzles
- Better sig checks to prevent common attacks
- Python wrapper for unit testing the clsp and to actually test this on chain
- so much stuff

## Acknowledgements
Thank you to the Clovyr team for a great platform to develop on. Definitely streamlined the onboarding to get coding right away given there were only 24 hours.

Thank you to the Chia team for creating awesome searchable docs and videos. And thank you for the live support.
