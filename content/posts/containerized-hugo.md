---
title: "Containerized Hugo Workflow"
description: "Using Docker Compose to preview the site while GitHub Pages handles deployment."
date: 2025-02-14T12:00:00Z
draft: true
tags: ["hugo", "docker", "development"]
categories: ["tooling"]
---

The blog now ships with a Docker Compose setup, so you can run `docker compose up hugo` and immediately view the site at `http://localhost:1313`. The container mounts the repository into `/src`, watches for file changes, and reloads the browser as you edit content.

When you are ready to publish, commit your changes and push to `main`. GitHub Actions will build the Hugo site with the same container-friendly config, then deploy it to GitHub Pages.
