# Astro Blogging / Content Admin Review

## Summary

Astro works well for file-based blogging and static content publishing. In the prototype, it handled Markdown posts, MDX posts, typed frontmatter, dynamic blog routes, tag routes, draft filtering, and production builds cleanly.

However, Astro is not a Ghost-like CMS by itself. It does not provide a built-in content editor, admin dashboard, user roles, newsletter/membership features, comments, or editorial workflow. To replace Ghost's admin experience, Astro needs an additional CMS layer.

## Prototype Tested

The prototype includes:

- Home page: `/`
- Blog index: `/blog`
- Blog post detail pages: `/blog/[slug]`
- Tag pages: `/tags/[tag]`
- About page: `/about`
- Markdown content: `first-post.md`
- MDX content with an Astro component: `second-post.mdx`
- Draft content hidden from public routes: `draft-post.md`
- Typed frontmatter via Astro Content Collections
- Production build and preview

## What Works Out of the Box

Astro is a strong fit for the frontend/blog rendering layer:

- Static blog pages
- Markdown content
- MDX content
- Astro components inside MDX
- File-based routing
- Dynamic routes for posts and tags
- Frontmatter-driven metadata
- Typed frontmatter validation with Content Collections
- Draft filtering through application logic
- SEO-friendly static HTML
- Production build output

Astro also supports RSS and sitemap through official integrations:

- `@astrojs/rss`
- `@astrojs/sitemap`

## Content Collections Notes

Content Collections are the key feature for structured blogging in Astro. They allow us to define a schema for post frontmatter, including:

- `title`
- `description`
- `date`
- `author`
- `tags`
- `draft`

This makes Markdown/MDX content safer than plain files because invalid or missing metadata can fail during development/build.

In Astro v6, the prototype used an explicit content loader for the blog collection:

```ts
loader: glob({
  pattern: "**/*.{md,mdx}",
  base: "./src/content/blog",
});
```

## What Needs Integration

Astro does not include the content admin features Ghost provides:

- Admin/editor UI
- Non-technical writing workflow
- Preview/publish workflow
- User roles and permissions
- Newsletter/membership features
- Comments
- Media/editorial workflow
- Scheduled publishing

These require either a CMS integration or keeping Ghost as the CMS.

## CMS Options

| Option                  | Role                               | Fit                                              |
| ----------------------- | ---------------------------------- | ------------------------------------------------ |
| File-based Markdown/MDX | Simplest content source            | Best for developers/technical writers            |
| Keystatic               | Git/file-based content editor      | Strong Astro fit; worth prototyping              |
| Decap CMS               | Git-based admin UI                 | Good for basic editor workflow                   |
| TinaCMS                 | Git-backed CMS                     | More complete but more complex                   |
| Sanity / Contentful     | Headless CMS                       | More productized editor experience               |
| Ghost + Astro frontend  | Keep Ghost admin, replace frontend | Strong option if Ghost editor experience matters |

## Recommendation

Astro can replace Ghost's frontend/blog rendering layer. It is a strong fit if the site is mostly static, content-driven, SEO-oriented, and maintained by developers or technical writers.

Astro alone should not be treated as a full Ghost replacement because it does not include a built-in CMS/admin layer. If the goal is to replace Ghost's authoring and editorial experience, the next prototype should test Astro with a CMS.

I recommend testing one of these next:

1. Astro + Keystatic, if we want a file/Git-based workflow that stays close to the current prototype.
2. Astro + Decap CMS, if we want a simple admin UI for Markdown content.
3. Ghost as headless CMS + Astro frontend, if preserving the Ghost editor experience is important.

## Bottom Line

Astro works well for blogging and content-driven pages. It can replace the rendering/frontend part of Ghost. It needs a CMS integration to replace Ghost's content admin experience.
