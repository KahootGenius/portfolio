# 小莲 · XiaoLianBot

**A QQ group bot who looks after the group.**
[Code](https://github.com/KahootGenius/XiaoLianBot) · Python · QQ's official bot SDK · October 2026

## The problem

The group has a rule: anyone who goes 30 days without a real message, and isn't on leave or exempt, is
removed. Someone has to keep track of who last said something that counts, remind them, and follow
through. 小莲 does it so the admins don't have to.

## Who it helps

The admins, who no longer track activity by hand. And the members, who get a clear rule, a reminder
before anything happens, a way to ask for leave, and a say over what she remembers about them.

## What I built

小莲 grew out of my earlier [Castorice bot](https://github.com/KahootGenius/Castorice_bot) into the
group's gentle, slightly scatterbrained caretaker:

- **She reads every message** and judges whether it counts. Discussion, questions, answers, links and
  files do; stickers, check-ins and copy-paste don't. On day 25 she sends one reminder; on day 30,
  removal.
- **Safety comes first.** There are three modes: report only, an admin approves each day's list with one
  reply, or automatic. She never removes the owner, admins, exempt members or anyone on leave, removes
  at most 15 people a day, and stops and alerts the admins if too many come due at once.
- **A member table** shows admins who has been quiet and why a message didn't count, in a browser or
  inside QQ.
- **She chats in character**, with memories members can list and delete with one command, and nobody
  can plant instructions in her through them.
- **She runs the team games**, where captains pick their teams.

**How it was made.** Most of the code was written by Claude Code at my direction; those commits carry
its co-author tag.

## The result

<!-- TODO: what changed in the group? How long has she been running, how many members, how much admin time saved? -->

_Coming soon — in my own words._

## What I learned

<!-- TODO: technical and personal. -->

_Coming soon — in my own words._
