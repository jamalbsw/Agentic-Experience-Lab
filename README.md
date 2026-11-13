# AXD Lab

A step-by-step learning path for designers new to agentic experience design. Static site, no build step, hosted on GitHub Pages.

**[Open the AXD Lab site](https://jamalbsw.github.io/Agentic-Experience-Lab/)**

The site is password protected. Ask the onboarding contact for the team password. It is never stored in this repository.

## What's in this repository

- `public/index.html` the password gate. The guide inside it is compressed and encrypted (AES-256-GCM, key derived from the password with PBKDF2-SHA256, 600,000 iterations).
- `public/.nojekyll` tells GitHub Pages to serve files as they are.
- `.github/workflows/pages.yml` deploys `public/` to GitHub Pages on every push to `main`.

The readable source and the build script are kept outside this repository so the content stays private.

## Updating the guide

1. Edit the source `index.html`.
2. Rebuild the gate: `node build-gate.mjs index.html public/index.html "<team password>"`.
3. Commit `public/index.html` to `main`. The workflow redeploys in about a minute.
4. To change the password, rebuild with the new one and share it with the team.
