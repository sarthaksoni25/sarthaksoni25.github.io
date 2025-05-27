---
title: "Getting Google OAuth Working with HTTPS, CORS, and SQLite"
mathjax: true
layout: post
---

Following up from my last post, I have set up the Google OAuth.

It took a while for me to get the hang of the flow. Managing HTTPS, HTTP, and CORS issues is a pain. POST requests on HTTP get blocked during Gmail authentication.

We have an HTTP Node server, and Nginx now handles SSL. Used CORS to manage allowed origins. There are a lot of moving parts now. It's harder to debug stuff. What helps is understanding what part is working correctly and narrowing down the scope of the problem—especially with these CORS errors. Sometimes the frontend breaks, sometimes the backend breaks.

I have a `/ping` endpoint to verify if the backend works and returns "pong". That really came in handy.

As of now:
- Local development works via Vite proxy.
- Production works with Nginx and HTTPS.
- All CORS, proxy, and HTTPS concerns are cleanly separated.

P.S. Don't forget to add `localhost` in the Google Cloud Console for the authentication client IDs.

I also set up a SQL database. Currently, I'm using `better-sqlite3`, since our app is pretty lightweight.

We've moved away from that hacky JSON thing now. So we have a proper database ready.

---

### ✅ Next Things to Work On

1. **Docker**  
   I was exploring Docker for my work stuff. Could probably set it up in the server.

2. **Observability**  
   Had a few issues with debugging logs in the server. Probably explore and see if there are good open-source dashboard options.
