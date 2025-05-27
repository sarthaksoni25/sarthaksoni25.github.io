---
title: "AddVenture is Live at add-venture.xyz!"
mathjax: true
layout: post
---

Following up from my last post, we officially have a domain name: [https://www.add-venture.xyz/](https://www.add-venture.xyz/)

I bought it from Hostinger for ₹250 for the first year. Hopefully I remember to cancel it—otherwise, they’ll charge ₹1000 for the next year.

Anyway, as you can see, I’ve also added HTTPS security.

Deploying the website was quite a pain. When I started, ChatGPT had suggested that I go for EC2 for the backend and S3 for the frontend. But that turned out to be overkill for now.

Plus, I had already set up the frontend and backend workflows in Git. But that’s okay—it’s for the better. Eventually, if we really have to scale the app, frontend and backend decoupling is the right way to go.

So currently, my infra setup looks like this:

User (Browser) <br>
↓<br>
DNS Resolution (Hostinger)<br>
↓<br>
CNAME www → CloudFront<br>
↓<br>
CloudFront (HTTPS via ACM)<br>
↓<br>
S3 / Backend / API (origin)<br>


Looks pretty neat. This is now a good playable game, at least for starters.

---

### ✅ Next Things to Work On

1. **OAuth** so that there’s a history for users  
2. **Global leaderboard**  
3. **Database** to store this information  