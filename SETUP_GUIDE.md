# 🛠️ How to Set Up This Repo on GitHub

Follow these steps once. It also doubles as Git practice (Phase 1, Week 4).

## 1. Create the repo on GitHub
- Go to github.com → New repository
- Name it something like `ml-engineering-journey`
- Set to **Public**
- Don't initialize with README (you already have one)

## 2. Push these files
From inside this folder, in your terminal:

```bash
git init
git add .
git commit -m "chore: initialize learning journal"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/ml-engineering-journey.git
git push -u origin main
```

## 3. Daily workflow (the habit)
Each day after studying:

```bash
# copy the template into a new dated entry
cp daily-log/_TEMPLATE.md daily-log/day-02-2026-07-04.md
# fill it in, then:
git add .
git commit -m "log: day 02 — OOP inheritance"
git push
```

That daily push = a green square = visible consistency.

## 4. Weekly (every Sunday)
- Fill in a weekly review from the template
- Update the progress snapshot in the main README
- Commit & push

## Tips
- **Keep entries short.** 5 minutes max. A journal you keep beats a perfect one you abandon.
- **Commit message convention:** `log:` for daily entries, `notes:` for concept notes, `chore:` for housekeeping, `feat:` for project work. Good practice for real repos.
- **Don't break the chain.** Even a 1-line entry on a hard day keeps momentum.
- **Never commit data or secrets** — the .gitignore handles the common cases, but stay alert.
