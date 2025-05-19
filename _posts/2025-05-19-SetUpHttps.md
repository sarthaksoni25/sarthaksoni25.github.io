---
title: "Setting Up CI/CD Pipelines for AddVenture"
mathjax: true
layout: post
---

Following up from my last post, we officially have a domain name: https://www.add-venture.xyz/

I bought it from Hostinger for ₹250 for the first year. Hopefully I remember to cancel it—otherwise, they’ll charge ₹1000 for the next year.

Anyway, as you can see, I’ve also added HTTPS security.

Deploying the website was quite a pain. When I started, ChatGPT had suggested that I go for EC2 for the backend and S3 for the frontend. But that turned out to be overkill for now.

Plus, I had already set up the frontend and backend workflows in Git. But that’s okay—it’s for the better. Eventually, if we really have to scale the app, frontend and backend decoupling is the right way to go.

So currently, my infra setup looks like:

User (Browser)
↓
DNS Resolution (Hostinger)
↓
CNAME www → CloudFront
↓
CloudFront (HTTPS via ACM)
↓
S3 / Backend / API (origin)

Looks pretty neat. This is now a good playable game, at least for starters.

**Next things to work on:**
1. OAuth so that there’s a history for users  
2. Set up a global leaderboard  
3. Set up a database for storing this information  