# LoveSeek

**An AI companion that keeps a life of her own.**
[Code](https://github.com/KahootGenius/OpenLoveSeek) · TypeScript · React Native · Android · July–October 2026

## The problem

The companion chat apps I tried forgot things constantly and had no sense of time. One had a messy
interface and messier settings, and its character messaged me at 4 a.m. So I built my own. It was also
a way to learn two things by building them: calling large language models, and context management,
which means deciding what part of a long conversation each request should carry.

## Who it helps

People who want a companion that remembers what they said and keeps believable hours. Most of my users
don't read English well or can't reach GitHub easily, so the builds go out as an Android app file in the
LoveSeek QQ group. There is no server and no account: chats and memories are stored only on the phone,
and each user brings their own model key. All 43 of the app's instruction prompts can be read and
edited inside it, because I think people have the right to know what is sent with their own key.

## What I built

A chat app for Android where the characters are run by language models. A character follows a daily
schedule, carries her mood and private thoughts from one message to the next, remembers what matters
to you, posts to a social feed and talks with other characters in group chats. She replies when she
would actually see your message: send one at 1 a.m. and she answers after she wakes up.

**How it was made.** I designed LoveSeek and tested it; Claude Code, Anthropic's coding agent, wrote the
code. Every version followed the same loop. I asked for a feature or reported a bug I had seen on my
phone, Claude Code recommended a design, and I approved it, changed it or sent it back. Then it was
built with tests, and I installed the build and used it every day. Each wave's written spec records who
decided what.

## The result

- **790 downloads** of 8 builds, by the QQ group's own counter; 202 of them are v3.0.
- **v1.0 on July 14, v3.0 on September 15**, through 15 written specs.
- **654 automated tests**, all passing, for about 18,000 lines of TypeScript.
- **0 servers.** Nothing leaves the phone except the requests to the user's own model provider.

## What I learned

At first I fixed problems by adding instructions to the prompt. By v2.9 there were up to sixteen
unranked sections, and the model ignored the rules that mattered most, like keeping casual replies
short. Now a rule that must always hold lives in code, and the prompt carries only what a model does
well. When she's asleep, code holds her reply until she wakes, so there's nothing for the model to bend.

What I'm least satisfied with is memory. A fact in her memory vault stays exact for as long as it's
there, and anything else fades or comes back changed. That's forgetting like a database, not like a
person.
