# Waste Land 2039

**A zombie horde that learns where you run.**
[Code and full write-up](https://github.com/KahootGenius/WasteLand2039) · C# · Unity · Python · the experiment ran September–October 2026

## The problem

Waste Land 2039 is my 2D top-down survival game, made in Unity: you defend a base for up to 30 days,
and each day can bring a zombie horde. The player is faster than the zombies (speed 5 against 3), so a
zombie chasing a fleeing player never catches up. The only way to catch a runner is to be on their
route *before* they run. That turns "learn the player" into something I can measure:

> Can a zombie horde learn how *this* player escapes, and be waiting there before they arrive?

## Who it helps

Players: a horde that learns how you play stays a challenge after you've learned it. And anyone
building game AI, because the write-up records what didn't work as carefully as what did.

## What I built

The zombies' brain became swappable, so different "commanders" could be tested against each other
under the same rules:

- **Baseline**: the game's original scripted AI.
- **V1**: a reinforcement-learning policy that learned by trial and error.
- **V2**: a small model that counts where this player has run before, plus scripted ambush tactics.
- **V2 Full** (October 20–26): V2 with the ambush sized to the player's style, and chasers that cut a
  runner off instead of following.

A person escapes only a few dozen times a session, far too few to learn from or to test on. So the
commanders played against bots that drive the real player controller under the same rules as a
person, in eight arenas at once, at 25 to 38 times real speed.

**Who did what.** The idea, the plan, the decision at each step, every evaluation run, the adaptive
add-ons and all of the October 20–26 work are mine. Claude Code wrote the tracker, the player profile,
the arena, the first bots, V1, V2 and the earlier reports, at my request. The repo's
[credits](https://github.com/KahootGenius/WasteLand2039#credits) list it file by file.

## The result

- **V2 learned to anticipate; V1 never did.** Reinforcement learning learned to be lethal, but not to
  be waiting on the route.
- **Three adaptive add-ons to V2 didn't help** across four controlled runs, and the write-up says so.
- **V2 Full did 4.4 more damage per wave than V2** (95% interval +3.0 to +5.8) in a test whose success
  criteria I wrote before the run. That is 12% more overall, and 40% more against a bot that avoids
  routes where it was caught.

## What I learned

- **An AI learns what its reward pays for.** V1's reward didn't separate waiting on a route from running
  a player down, and chasing is easier to discover.
- **Splitting the job beat learning it end to end.** A counting model plus scripted tactics passed the
  test that reinforcement learning failed, without a training budget.
- **Build the ground truth before optimizing.** The easy measurements misled me at every step.
- **Forecast, then pre-register.** My simulator forecast +5.6, the run gave +4.4, and the criteria
  written beforehand already expected about +4.

**Limits.** Every test used bots, not people, on one arena layout. Playtests with real players are the
obvious next step.
