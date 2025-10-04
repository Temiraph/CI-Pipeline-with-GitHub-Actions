# CI Pipeline with GitHub Actions

[![CI](https://github.com/Temiraph/CI-Pipeline-with-GitHub-Actions/actions/workflows/ci.yml/badge.svg)](https://github.com/Temiraph/CI-Pipeline-with-GitHub-Actions/actions)

A simple, lightweight Continuous Integration (CI) pipeline for a Node.js project using GitHub Actions.  
Automatically runs on push, pull requests, and nightly schedules to detect issues early.

---

## 🚀 What it does

- Runs tests on **Node.js 20 & 22** via a matrix strategy  
- Triggers on `push`, `pull_request`, `schedule` (nightly), and manual dispatch  
- Uses npm caching (based on `package-lock.json`) for faster installs  
- Prevents duplicate workflow runs (via concurrency settings)  
- Clean setup with minimal permissions  

---

## 🧰 Setup & Usage

1. Clone or fork this repo  
2. Install dependencies:  
   ```bash
   npm install
Run tests locally

npm test


Push a commit or open a PR — CI runs automatically.

Project scripts

npm test — runs a minimal smoke test (Node’s built-in test runner)

CI details (./.github/workflows/ci.yml)

Uses actions/checkout@v4 and actions/setup-node@v4

Caches npm based on package-lock.json

Matrix strategy for Node 20 & 22

Scheduled cron (02:30 UTC by default)

Troubleshooting

Cache step failing ➜ Ensure package-lock.json is committed.

PR shows 0 checks ➜ If PR is to an upstream repo, CI may require maintainer approval. PR within your fork will run immediately.

Why multiple checks? ➜ Matrix (2 Node versions) × Events (push + PR) = multiple runs.

