---
title: "Catching Cheaters on Add‑Venture"
mathjax: true
layout: post
---

I’ve officially started beta‑testing **Add‑Venture**.  
Before putting it on Show HN I shared it with my developer friend, **Vishesh**.  
Being the awesome friend he is, he immediately began competing with me for the top score—and I beat him fair and square.

Then he realised my backend API was exposed. A quick peek at the browser’s **Network** tab let him post a fake score, knocking me off the leaderboard. Time to tighten things up.

## The fix

I added a compact JWT security layer:

* **`authenticate` middleware** (JWT + HS256) that  
  * verifies the `Authorization: Bearer <token>` header, and  
  * pulls `{ guestId, name, isGuest }` into `req.user`.

I almost added a **`banned`** flag in the database, but for a casual game that felt like overkill—for now.

Happy hacking, and see you on the (now honest) leaderboard!
