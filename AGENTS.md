# AGENTS.md

## Scope

These instructions apply to the whole repository.

## Project Overview

This repository is for `hcscat.github.io`, a personal GitHub Pages blog/portfolio site.
This Codex thread is dedicated to adding, editing, and maintaining that GitHub Pages blog.
At the time of the latest inspection on 2026-06-05, the active site source is an Astro project in `site/`.
The current public direction is a Korean HCS portfolio site with blog-style work notes and separate project case studies.
Other Codex sessions may also work in this repository, and the blog architecture, platform, source layout, or deployment approach may change.
Always re-check the current repository state before making assumptions.

## Main Structure

- `site/`: Astro 5 blog/portfolio source. Make normal website changes here.
- `site/src/pages/`: Route pages such as the home page, about page, blog listing, and project listing.
- `site/src/pages/projects/`: Project listing and project detail routes.
- `site/src/content/blog/`: Markdown/MDX blog posts and work notes.
- `site/src/content/projects/`: Markdown/MDX portfolio project case studies.
- `site/src/components/`: Shared UI such as header, footer, metadata, date formatting.
- `site/src/layouts/`: Page layouts, currently the blog post layout.
- `site/src/assets/`: Images imported by Astro content/pages.
- `site/public/`: Static files served from the web root, such as favicon and fonts.
- `docs/`: MkDocs notes/source plus older generated-looking static output. Do not edit this for the main Astro blog unless the task explicitly mentions notes/MkDocs.
- `.github/workflows/deploy.yml`: GitHub Pages deployment workflow.

## Content Editing Guide

- Site title and description: edit `site/src/consts.ts`.
- Home/landing content: edit `site/src/pages/index.astro`.
- Bio/about page: edit `site/src/pages/about.astro`.
- Blog posts and work notes: add or edit files in `site/src/content/blog/`.
- Blog post required frontmatter: `title`, `description`, `pubDate`.
- Blog post optional frontmatter: `updatedDate`, `heroImage`.
- Portfolio project case studies: add or edit files in `site/src/content/projects/`.
- Project required frontmatter: `title`, `description`, `pubDate`, `period`, `role`, `stack`, `summary`, `highlights`, `order`.
- Project optional/defaulted frontmatter: `updatedDate`, `featured`, `confidentialityNote`.
- Home featured projects come from the `projects` collection where `featured` is true, sorted by `order`.
- Header navigation and social links: edit `site/src/components/Header.astro`.
- Footer name/social links: edit `site/src/components/Footer.astro`.
- SEO/Open Graph defaults: edit `site/src/components/BaseHead.astro`.
- Global visual styling: edit `site/src/styles/global.css`.

## Commands

Run these from `site/`:

- `npm ci`
- `npm run dev`
- `npm run build`
- `npm run preview`

The deploy workflow runs Node 20, executes install/build commands from `site/`, and uploads `site/dist` to GitHub Pages.

## Working Notes

- Prefer the current platform and patterns present in the repository. Do not assume Astro remains authoritative if the structure has changed.
- Check `git status` and relevant config files before editing, because other sessions may have modified the project.
- Keep generated build output out of commits; `dist` is ignored.
- Keep public portfolio content in Korean unless the requested task says otherwise.
- Do not expose confidential customer, employer, internal URL, system screen, or personal contact details. Use sanitized summaries for career/project content.
- Replace any remaining starter Astro placeholder images before treating the site as production-ready.
- When the Astro structure is still active, add portfolio projects in `site/src/content/projects/` and blog/work notes in `site/src/content/blog/` unless a custom route/page is specifically needed.
- Keep edits scoped; avoid changing `docs/` unless the requested task is about MkDocs notes.
