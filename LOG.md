# Work Log

A running, dated journal of what I build and *why*. Newest entries on top.

Each entry: what I worked on, the motivation, and what I learned or what changed.

---

## 2026-10-26 — Filled in the portfolio

- Added the four projects I've worked on since June, each with a plain-language page drafted with
  Claude Code from the repos, and back-filled this log from their commit histories.
- **Next:** write the About in my own words.

## 2026-10-25 → 26 — 小莲, a caretaker for a QQ group

- Turned my Castorice bot into 小莲 with Claude Code. She enforces the group's 30-day activity rule
  behind safety rails, runs the team games, and chats in character with memories members can see
  and delete.
- **Why:** so the admins don't have to enforce the rule by hand.

## 2026-10-20 → 26 — Waste Land 2039: V2 Full

- Gave the test bots only what a player can see, sized the ambush to each player's style, and made
  the chasers cut a runner off instead of following.
- Wrote the success criteria before the run. V2 Full did 4.4 more damage per wave than V2
  (95% interval +3.0 to +5.8), 12% more overall.
- Merged both experiment branches into `main`.
- **Learned:** forecast, then pre-register. My simulator said +5.6; the real run said +4.4.

## 2026-10-19 → 24 — LoveSeek fixes

- Found two bugs while planning the demo video, held replies and read-receipt order, and chose the
  fixes.
- Claude Code fixed memories from the perception call skipping the vault's 40-entry cap.

## 2026-10-08 → 12 — RL for KARDS, stages 1 to 3

- A fast engine for a KARDS-style card game, and bots that learn it by self-play, in three stages of
  growing rules. Claude Code's agents wrote the code; I ran the training on my own PC.
- Stage 3's Transformer policy beat the lookahead-search bot in 91.6% of 2,000 games and passed all
  four done criteria.
- **Why:** trying to beat the game.
- **Learned:** halving the learning rate gained more than any change to the network.

## 2026-09-24 → 10-18 — Waste Land 2039: can a horde learn where I run?

- Set up the experiment. Claude Code built the arena, the bots, a reinforcement-learning commander
  (V1) and a small predictive model with scripted tactics (V2); the plan, the adaptive add-ons and
  every evaluation run were mine.
- V2 learned to anticipate; V1 learned to be lethal but never to wait on the route. Three adaptive
  add-ons to V2 didn't help, and the write-up says so.
- **Why:** the player outruns every zombie, so being on the escape route first is the only way to
  catch them. That makes "learn the player" something I can measure.
- **Learned:** build the ground truth before optimizing. The easy measurements misled me at every step.

## 2026-09-13 → 10-03 — LoveSeek v2.9 and v3.0

- v2.9 added a second model provider and Quick Start personas. v3.0 added liveliness: replies on her
  schedule, a generated day, and follow-ups on what you told her.
- Shared v3.0 in the LoveSeek QQ group on September 15 and released it on GitHub on October 3.
- **Learned:** a rule that must always hold belongs in code, not in the prompt.

## 2026-08-16 — Open-sourced LoveSeek

- Published the app's code as [OpenLoveSeek](https://github.com/KahootGenius/OpenLoveSeek), so anyone
  can build it themselves.

## 2026-07-14 → 22 — LoveSeek v1.0 to v2.8

- Designed an Android AI companion app and tested every build on my phone; Claude Code wrote the code.
- In nine days it grew from a plain chat app into characters with schedules, memories, a feed, group
  chats, photos and voice.
- **Why:** the companion apps I'd tried forgot everything and had no sense of time. One messaged me
  at 4 a.m.

## 2026-06-03 — Set up the portfolio

- Created this repository as the home for my projects.
- **Why:** I want a clear, honest record of my work — judged not just on the code, but on
  the real-world impact and the thinking behind it.
- **Next:** decide the first project worth building.
