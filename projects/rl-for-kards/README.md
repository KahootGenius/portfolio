# RL for KARDS

**A card-game AI that learns by playing itself.**
[Code](https://github.com/KahootGenius/RL-for-KARDS) · Python · PyTorch · October 2026

## The problem

KARDS is a two-player card game about a front line: each side deploys units, pushes forward and tries to
destroy the other's base, without seeing the other player's hand. Could a bot learn to play a game like
that well with no strategy written in, only by playing against itself and keeping what wins? The repo's
one-line description says it plainly: trying to beat the game.

## Who it helps

<!-- TODO: who is this for? -->

_Coming soon — in my own words._

## What I built

A fast engine for a KARDS-style card game, where the cards and decks are data and every rule lives in
one file, and four kinds of player: a random bot, a scripted greedy bot, a lookahead bot that tries each
move one step ahead, and a learning bot trained with PPO, a reinforcement-learning method. The game grew
in three stages:

| Stage | The game | The learning bot |
|---|---|---|
| 1 | Plain units, two fixed decks | Beat the greedy bot in 75.7% of 2,000 games |
| 2 | Unit types, traits and movement costs; 25 cards, 4 decks | Passed its done criteria on all three training runs |
| 3 | Card effects, choices and the mulligan; 55 cards, random 40-card decks | A Transformer policy beat the lookahead bot in 91.6% of 2,000 games |

**How it was made.** Claude Code's agents wrote the engine, the bots and their tests, phase by phase. I
set the goals, ran every training run on my own PC (each takes hours) and checked the results.

## The result

Stage 3's reference model passes all four of its done criteria. It beats the lookahead bot in 91.6% of
games on random decks (the bar was 70%), wins at least 86.9% in every fixed deck pairing (the bar was
60%), beats a simpler network head to head, which held up over 10,000 fresh games, and solves 15 of 20
tactical puzzles (the bar was more than half).

The real game is the next step: 68 of 110 real KARDS cards from a sample already fit the engine's card
format, and the rest show what it still needs.

## What I learned

- **Tuning can matter more than design.** Halving the learning rate gained more than any change to the
  network.
- **A narrow win needs fresh games.** The Transformer's edge over the simpler network was small, and it
  was picked from several runs scored on the same deals. So it was replayed on 10,000 deals no run had
  seen, and it held, at about 51%.
- **Going first still decides a lot.** The first player wins about 70% of self-play games.
