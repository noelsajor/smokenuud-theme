Smokenuud Shopify Theme

A fully version-controlled Shopify theme for the Smokenuud store, built with a modern local development workflow using Shopify CLI 3.x, Git branching, Liquid linting, and Prettier formatting.
This repo includes a safe multi-environment setup: development → staging → production.

🚀 Development Workflow Overview

This theme uses 3 Shopify environments:

Branch	Shopify Theme	Shopify ID	Purpose
main	NUUD-Refresh	153917686009	Live production site
staging	NUUD-Staging	154968195321	QA, approvals, pre-production
dev	Development (bf4285-MacBook-Pro)	154963542265	Local development & testing

This structure ensures:

You never break the live site

All changes are reviewed before publishing

Every update is tracked and backed up in GitHub

🛠️ Installation & Setup
1. Clone the repo
git clone https://github.com/noelsajor/smokenuud-theme.git
cd smokenuud-theme

2. Install dependencies
brew tap shopify/shopify
brew install shopify-cli

3. Log in to Shopify
shopify login --store smokenuud.myshopify.com

4. Pull the correct theme (optional)
shopify theme pull --theme 154963542265

🎨 Local Development

Work inside the dev branch:

git checkout dev
shopify theme dev --theme 154963542265


This opens a local preview with hot-reload:

http://127.0.0.1:9292


Your changes update instantly — nothing touches the live site.

📦 Pushing Changes
✅ Push to Dev theme (safe)
git checkout dev
shopify theme push --theme 154963542265
git add .
git commit -m "Update section"
git push

🟡 Push to Staging (for approval)
git checkout staging
git merge dev
shopify theme push --theme 154968195321
git push

🔴 Push to Production (live)
git checkout main
git merge staging
shopify theme push --theme 153917686009
git push

📁 Project Structure
.
├── assets/
├── config/
├── layout/
├── locales/
├── sections/
├── snippets/
├── templates/
├── .gitignore
├── .prettierrc
├── .theme-check.yml
└── README.md

✨ VS Code Recommended Extensions

Shopify Liquid Template Snippets

Liquid

Prettier

Prettier Liquid

Shopify Theme Check

GitLens

Path Intellisense

🧹 Formatting & Linting
Format Liquid, HTML, CSS, JS on save:

.prettierrc is included.

Theme linting:
shopify theme check

🔄 Automatic Backups (optional)
./backup-theme.sh


Creates timestamped backups inside /backups.

❤️ Contributions

Designed for future-proof, scalable, high-performance Shopify development.
Feel free to open issues or improve the workflow.