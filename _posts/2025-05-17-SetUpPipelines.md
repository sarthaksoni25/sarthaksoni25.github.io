---
title: "Setting Up CI/CD Pipelines for AddVenture"
mathjax: true
layout: post
---

Following up from my last post, I’ve added a basic authentication screen to AddVenture. No database yet; it's all temporary for now.

I also integrated Ant Design to clean up the UI a bit.

Here’s how it looks currently:

![Login Screen](/assets/Login.png)

![Game History](/assets/GameHistory.png)

---

I set up CI/CD pipelines using YAML workflows in GitHub. The frontend is built with `npm run build` and deployed to an S3 bucket.

💡 One hiccup I ran into: `.env.production` was in `.gitignore`, so GitHub Actions didn’t pick up the API URL. Had to fix that by committing the file.

For the backend (hosted on EC2), I’m using SSH via a `.pem` file. GitHub Actions uses this private key to connect, pull the latest code, and restart the server with `pm2`.

Still rough around the edges, but the pipeline is live and working. Pretty cool to see it deploy cleanly with every push to `main`.

Next things to work on is:
1) HTTPS since it's still insecure with http
2) Global Leaderboard
3) Proper authentication

Stay tuned