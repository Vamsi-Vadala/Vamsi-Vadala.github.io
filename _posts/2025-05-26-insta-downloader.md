---
title: "Instagram Saved Downloader - Web App"
date: 2025-05-26
categories: [Projects, Python]
tags: [Instagram, Automation, Web App, ffmpeg, Selenium, Flask]
---

## 🧠 Why I Built This

Let me start by saying — Instagram does **not** make it easy to batch-download your saved videos. Scrolling through hundreds of clips and screen recording them one by one felt like digital caveman behavior. So, I decided: *“Enough is enough, I’m making an app for this.”*

Enter: **Insta Saved Downloader** — a web-based tool that helps you fetch and download all your saved Instagram videos, either one at a time or in glorious batches.

---

## 💡 The Idea

I had 3 goals:
1. Make it easy to use (even for my non-coder sister).
2. Run it on my own laptop with no shady Chrome extensions.
3. Keep it aesthetic — because what’s the point if it looks like it was made in 2002?

---

## 🔨 How It Works

- Built using **Flask** for the web interface.
- Uses **Selenium** to log into Instagram and extract video links.
- Automatically picks the highest bitrate using **ffmpeg-python**.
- Merges audio + video where needed.
- Supports both:
  - single URL input
  - uploading a `.txt` file with multiple saved post URLs (playlist-style)

A breif explanation and architecture breakdown is provided here [Detailed Explanation of Insta Downloader Web App](https://vamsi-vadala.github.io/posts/instagram-downloader/)

---

## 🧪 My First Version (Painful but Progress)

The initial version was a CLI tool. It worked… until it didn’t.

```bash
> python old_script.py
Enter Instagram post URL:
```

Yeah — no progress bar, no feedback, just vibes.

Then I added a progress bar... that broke in the middle of long downloads.

And that's when it hit me: **let’s make it a web app**.

---

## 🖥️ The Web UI

I used Flask with Bootstrap, gave it a dark mode futuristic glow-up, and added flash messages so users aren’t guessing what’s happening.

### Features:
- Paste a link → click download
- Upload `.txt` of links → bulk download
- See progress + success messages in style
- Automatically merges audio/video using `ffmpeg`

---

## 🛠️ Lessons Learned

- Dealing with headless Chrome, cookies, and login flows was harder than expected.
- `ffmpeg` is both a blessing and a beast (especially syncing audio streams).
- Making a bash script that *actually* works across machines takes more patience than coding the backend.

---

## 🧰 Tech Stack

- Python 3.10
- Flask
- Selenium
- FFmpeg
- tqdm + progressbar
- waitress (for production server)

---

## 🤖 Automation Script

Created a bash script that:
- Installs dependencies
- Creates a `.venv` if it doesn’t exist
- Checks for `ffmpeg`
- Launches the app and opens the browser

Even throws red/yellow/green logs with emoji... because why not?

---

## ⚠️ Use With Caution

This tool is meant for **educational/personal use only**.

> Downloading content without permission might violate Instagram’s [Terms of Service](https://help.instagram.com/581066165581870).

Cookies help you log in without raising alarms — as powerful as logia fruit type it can't escape from Haki. Instagram can still detect suspicious behavior. So pace yourself and don’t go full Thanos on your saved posts. 💀

---

## ✅ Final Thoughts

This project was fun, frustrating, and full of learning. If you’re looking to automate your saved reels/videos for archiving or just for fun — feel free to clone, use, or improve it.

**🔗 GitHub**: [Insta Web Downloader](https://github.com/Vamsi-Vadala/insta-saved-downloader)

Pull requests welcome.
