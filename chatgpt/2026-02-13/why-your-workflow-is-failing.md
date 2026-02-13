# ✅ Why Your Workflow Is Failing

> **Platform:** CHATGPT | **Date:** 13/02/2026, 15:40:41 | **Turns:** 2
> **Source:** [Open Original](https://chatgpt.com/c/698ef891-6d18-8322-bfa3-495786cf2e22)

---

## USER

name: 04 Deploy to AWS EC2

on:
#   push:
#     branches:
#       - main
  workflow_dispatch:

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Deploy to EC2
        uses: appleboy/ssh-action@v1.2.5
        with:
          # Make sure these secrets are set in your repository settings!
          host: ${{ secrets.EC2_HOST }}
          username: ${{ secrets.EC2_USERNAME }}
          key: ${{ secrets.EC2_SSH_KEY }}
          script: |
            # Pull latest changes
            cd /home/ubuntu/colour-fun
            git pull origin main

            # Build frontend
            cd app
            npm install
            npm run build
            # Assuming Nginx is serving the build folder directly
            # or copy to /var/www/html
            sudo cp -r dist/* /var/www/html/ this is my workflow why is it failing

---

## ASSISTANT

Got you — and honestly your workflow is *very close*, but it’s failing because of one or more **classic EC2 GitHub Actions deployment traps**.
Let’s break it down like an elite deploy engineer 👇

✅ Why Your Workflow Is Failing
Your YAML is syntactically fine — the failure is almost certainly happening inside this SSH script:

```
bashCopy codecd /home/ubuntu/colour-fun
git pull origin main
cd app
npm install
npm run build
sudo cp -r dist/* /var/www/html/
```

So the question becomes:
❌ Which of these commands is crashing?

🔥 Most Common Reasons This Workflow Fails

1. **The folder doesn’t exist on EC2**

```
bashCopy codecd /home/ubuntu/colour-fun
```

If that directory isn’t present, SSH stops immediately.
✅ Fix: Make sure repo exists there:

```
bashCopy codels /home/ubuntu/
```

If not cloned:

```
bashCopy codegit clone your-repo-url colour-fun
```


2. **Git pull fails because EC2 has no GitHub auth**
Your EC2 instance must have permission to pull.
If the repo is private, `git pull` will fail with:

```
vbnetCopy codePermission denied (publickey)
fatal: could not read from remote repository
```

✅ Fix: Use SSH remote URL inside EC2:

```
bashCopy codegit remote set-url origin git@github.com:USERNAME/REPO.git
```

Or add a deploy key.

3. **Node/NPM not installed on EC2**
Many Ubuntu EC2 servers don’t have Node.
Then this fails:

```
bashCopy codenpm install
```

Error:

```
bashCopy codenpm: command not found
```

✅ Fix:

```
bashCopy codesudo apt update
sudo apt install nodejs npm -y
```

Or install proper Node version:

```
bashCopy codecurl -fsSL https://deb.nodesource.com/se
```


---
*Archived by [StoreChat](https://github.com/Adi-gitX/StoreChat) on 2026-02-13*
