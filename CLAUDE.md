# Context

Read this first in every new chat or Claude Code session.

## What we're building
A personal website for a senior Java developer working at KFZTeile, where he publishes technical posts for developers interested in Java and Spring. The angle: notes from production on a large e-commerce platform, including where AI actually helps in everyday development.

## Our Git
- Design system: github.com/mahditilab/sample-design-system
  Tokens (`assets/tokens.css`), components (`assets/components.css`), the storybook (`storybook.html`), the design skill (`SKILL.md`), and page designs in `prototypes/`.
- Website: github.com/mahditilab/sample-website
  The pages Claude Code builds. `main` is the live site, `staging` is the rehearsal, every change goes through a pull request.
- The design system repository is the source of truth. The website only uses what is in it.

## Stack
Plain HTML, CSS and a little JavaScript. No build step. Hosted on Netlify, connected to the website repository. The contact form uses Netlify Forms.

## Pages
`index.html` (home) · `blog.html` (list of posts) · `about.html` · `contact.html` · `thanks.html` (after the form). Prototypes exist for `home.html`, `blog.html` and `post.html`; the website pages are built from them. Each post is its own page built from `prototypes/post.html`. Code blocks inside posts are not defined yet: they need a decision in Claude chat first (monospace font, colours).

## Design inspiration
Three developer and designer portfolio templates were shared as references. They are inspiration only: no decision below is final until it is confirmed in Claude chat and recorded in the design system. The look is Orange (chosen): friendly and bold, Space Grotesk headlines, Inter text, orange accent, pill buttons, rounded cards. Do not copy their illustrations, photos, logos or exact layouts.

What we take from them:
- **Home page order:** hero with name, role and one line about what I write, plus two buttons (read the blog, get in touch) · latest posts (three cards, link to all posts) · short about with a few traits · technologies strip · experience as a short timeline · how I work as steps · closing call to action with contact details.
- **Tone:** personal and direct ("Hi, I'm ..."), quiet confidence, plenty of white space.
- **Newsletter:** a small "get new posts" sign-up near the footer (from the second template).

What we leave out: invented numbers (projects, clients, support hours), skill percentage bars, carousels, testimonials unless real and approved, stock or generated photos of other people.

Images (added): the home hero is split, text left and a portrait right (`hero__grid`, `portrait`); latest-post cards and post pages carry a 16:9 image (`card__media`, `cover`). Files are in `assets/images/`. The portrait and the `sample-*.svg` images are placeholders; the real photo of Mahdi must be supplied.

Look: Orange is the chosen look and lives in `assets/tokens.css` and `storybook.html`. Rust (`assets/tokens-rust.css`, `storybook-rust.html`) and Sage (`assets/tokens-sage.css`, `storybook-sage.html`) are kept as unused variants. Changing the look again is a decision for Claude chat.

Not defined in the design system yet, so each needs a decision in Claude chat before anyone builds it:
- Technologies strip or tile grid
- Experience timeline
- Newsletter sign-up
- Tag chips for post topics
- Code blocks inside posts (monospace font, colours)

## How we work: the loop
1. Design in Claude chat: prototype the page, try versions, check phone and desktop.
2. Update the design system: anything reused or a rule goes into tokens, components, storybook and SKILL.md. The page goes into `prototypes/`.
3. Push the design system repository to GitHub.
4. Claude Code, in the website repository: get the latest design system, update tokens and components to match, build the page from its prototype, on a new branch.
5. Test on localhost: phone and desktop, every link, Lighthouse. Not OK? The report goes back to Claude chat.
6. Pull request, check the Netlify preview link, merge. The site goes live.

## Rules for Claude Code
- Never make a design decision. Colours, fonts, spacing, layout, copy, motion and imagery are decided in Claude chat and live in the design system or the prototype.
- If something isn't defined there, stop and ask. Offer two or three options with a short reason for each. Don't pick one yourself.
- Use only tokens from `assets/tokens.css` and components from `assets/components.css`. Never hard-code a value.
- Work on a branch, never directly on `main`.
- After building, run the site locally, test phone and desktop, and report what you built, what you tested and every open question, before opening a pull request.

## Current state
Done: design system based on starter-paper (tokens, components, storybook, SKILL.md), blog index and post prototypes, a Design System artifact in Claude. Not done: nothing is pushed to GitHub yet (the GitHub connector is off for the organisation), no website pages are built, the sample prototypes still use placeholder text and "Mahdi Tilab".
Next: confirm the home page order above, decide the undefined components, prototype `home.html` in Claude chat, then push the design system.
