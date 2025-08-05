![TaskNova Bot](https://github.com/varunaditya27/render-keepalive-bot/actions/workflows/telegram-ping.yml/badge.svg)
![EcoDose Backend](https://github.com/varunaditya27/render-keepalive-bot/actions/workflows/ecodose-ping.yml/badge.svg)


# ⚡ Render Keepalive Bot

**Prevent your Render-hosted applications from sleeping — automatically and reliably.**

This repository contains scheduled GitHub Actions that periodically ping the `/health` endpoints of my Flask-based projects deployed on [Render](https://render.com). The goal is to keep these applications active around the clock by simulating user activity, thereby avoiding the free-tier inactivity timeout.

---

## 🚀 How It Works

- Every 10 minutes, GitHub Actions execute a `curl` command targeting a lightweight public endpoint (`/health`) on each app.
- This periodic traffic is sufficient to reset Render's inactivity timer.
- Endpoint URLs are stored securely using GitHub Secrets, ensuring both security and modularity.
- The solution requires no third-party uptime monitoring services — it runs entirely within GitHub's infrastructure.

---

## 📡 Projects Being Kept Alive

| Project               | Description                                                  | Status     |
|-----------------------|--------------------------------------------------------------|------------|
| 🧠 **Telegram Task Bot** | Flask-powered Telegram bot for scheduling task reminders       | ✅ Active |
| 🌿 **EcoDose Backend**   | Backend for EcoDose — integrates Gemini API and ML components | ✅ Active |

---

## 🔐 Security & Design Highlights

- No URLs are hardcoded — endpoints are accessed via GitHub Secrets
- Pinged routes are non-sensitive and have no side effects (`/health`)
- This setup is scalable, maintainable, and entirely free under GitHub's Actions usage limits

---

## 🛠️ Setting Up a Similar Workflow

To implement this in your own projects:

1. Create a new GitHub Action under `.github/workflows/`
2. Define a `cron`-based schedule to ping your endpoint
3. Store your endpoint(s) securely using GitHub Secrets
4. That’s it — GitHub handles the automation

Refer to the workflows in this repo for an example.

---

## 🤔 Why Not Use UptimeRobot or Other Services?

- Render may deprioritize or block requests from known uptime monitoring services
- GitHub Actions use varied IP addresses, making them less likely to be filtered
- You maintain full control, without relying on external tools

---

## 👤 Author

Maintained by [**Varun Aditya**](https://github.com/varunaditya27)  
This project is part of a broader ecosystem of tools I’m building to improve backend reliability and developer productivity.
