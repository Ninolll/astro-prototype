# Astro Blogging Review Checklist

## Goal

Can Astro replace Ghost's blogging/content functionality for this website?

## Prototype Scope

- [x] Home page
- [x] Blog index page: `/blog`
- [x] Blog post page: `/blog/[slug]`
- [x] Tag page: `/tags/[tag]`
- [x] About page: `/about`
- [x] Markdown post
- [x] MDX post
- [x] Typed frontmatter with Content Collections
- [x] Draft filtering
- [x] Date sorting
- [x] Production build
- [x] Preview build

## Evaluation Questions

- [x] Can Astro build a blog?
- [x] Is Markdown/MDX authoring smooth?
- [x] Can frontmatter manage title, date, author, tags, excerpt/description, draft?
- [x] Is routing simple?
- [x] Is production build stable?
- [x] Does Astro support RSS/sitemap/SEO?
- [x] Does Astro include a built-in content admin?
- [x] If not, which CMS integration is most suitable?
- [x] Can the non-technical editor experience get close to Ghost?

## Findings

- Astro works well for file-based blogging.
- Markdown and MDX both worked in the prototype.
- MDX can embed Astro components.
- Content Collections validated frontmatter with a schema.
- Astro v6 required an explicit content loader for the blog collection.
- Blog list, post detail routes, tags, and draft filtering worked.
- Production build and preview worked.
- Basic SEO metadata was straightforward.
- RSS and sitemap are supported via official Astro integrations.
- Astro does not include a built-in Ghost-like content admin.
- Replacing Ghost's admin/editorial workflow requires a CMS integration.

## Initial Hypothesis

Astro can likely replace Ghost's frontend/blog rendering layer, especially for static content and developer-managed Markdown/MDX workflows.

Astro alone probably cannot replace Ghost's admin/editorial experience. Replacing that part likely requires a CMS integration such as Keystatic, Decap CMS, TinaCMS, Sanity, Contentful, or Ghost used as a headless CMS.
