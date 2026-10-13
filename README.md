A responsive React + TypeScript starter website for an independent computing education resource. Built with Vite and React Router for local development in VS Code on Windows.

## Implemented in this foundation release

- Responsive homepage and navigation with light/dark theme toggle.
- Search across project entries, tutorial topics, and student tools.
- Project directory with text search, category/technology/difficulty/status filters, sorting, URL query support, and clear-filter behavior.
- Reusable project cards and project guide pages with explicit example/planned status labels.
- Tutorial topic index, technology overview, resources outline page, and About/trust page.
- Student tools: Roadmap Builder with locally saved progress, SRS draft builder with Markdown download, Quality Checklist with local persistence, JSON Formatter/Validator, basic Markdown Previewer, Word Counter, and Technology Stack Advisor.
- Viva practice prompts with topic filters, answer reveal, and local practice notes in current page state.
- Bookmark projects, persist theme and selected tool progress in browser localStorage, clear ProjectLab local data from the footer.
- Responsive layouts, visible focus states, semantic navigation/labels, reduced-motion support, print stylesheet, page metadata, and a not-found route.

## Not yet implemented / honest limitations

- No backend, accounts, cross-device synchronization, analytics, or cloud backup.
- Contact/feedback submission is not configured. The footer explicitly indicates the contact method is not configured; replace the example address and configure a monitored mailbox before production.
- Tutorial entries are topic listings, not full articles yet. Resource entries are copyable outlines, not fabricated file downloads.
- Initial project entries are illustrative/planned. No sample implementation, database schema, or test results are claimed to exist or have been verified.
- Diagram editor, code execution/sandbox, CMS, server-side search, DOCX/PDF export, and automated content review are not part of this foundation release.
- SRS exports Markdown only. The Markdown preview supports a small safe subset rather than full Markdown.
- Search and directory query state are client-side; category and query parameters are preserved, while all filters are not currently serialized to the URL.

## Requirements

- Node.js 20 or newer recommended
- npm
- VS Code (recommended)

## Run on Windows

1. Extract the project folder.
2. Open the `projectlab` folder in VS Code.
3. Open **Terminal → New Terminal**.
4. Run:

   ```powershell
   npm install
   npm run dev
   ```

5. Open the local URL printed by Vite (usually `http://localhost:5173`).

## Production build

```powershell
npm run typecheck
npm run build
npm run preview
```

The production output is created in `dist/`.

## Content maintenance

Starter entries live in `src/data/content.ts`. Project records use a typed `Project` model with a stable slug, title, description, category, technology tags, difficulty, type, database, status, and effort note. Expand the schema as verified content becomes available. Never label a guide verified unless the relevant steps were actually checked in a documented environment.

## Local storage behavior

The `src/lib/storage.ts` helper namespaces local browser values under `projectlab:v1:`. Data is local to the current browser profile and is not synchronized. Clearing browser data can remove it. The footer's “Clear local data” action removes ProjectLab-namespaced values and reloads the app.

## Before public deployment

- Configure a real contact and correction channel.
- Add a real favicon and OG image.
- Verify all content, citations, links, and course-specific statements.
- Add tests and run typecheck/build in the target environment.
- Set deployment-specific canonical URL, sitemap, robots rules, security headers, and hosting fallback rules.
- Review accessibility with keyboard and assistive technology.
- Check current package versions and dependency security before shipping.
