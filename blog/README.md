# Adding a blog post

The blog is deliberately plain HTML so it works with the existing GitHub Pages
site and does not need a build system.

## 1. Copy the post template

From the repository root, run:

```sh
cp blog/posts/post-template.html blog/posts/2026-09-23-short-post-title.html
```

Use the publication date followed by a short lowercase title. Separate words
with hyphens.

## 2. Edit the new post

In the copied file:

1. Remove `<meta name="robots" content="noindex">` so search engines may index it.
2. Replace every `POST TITLE` with the post title.
3. Replace every `ONE-SENTENCE DESCRIPTION` with a short summary.
4. Replace `MONTH DAY, YEAR` with the publication date.
5. Replace the example text inside `<div class="prose">` with the post.

Use `<p>...</p>` for paragraphs and `<h2>...</h2>` for section headings.

## 3. Add the post to the blog page

Open `blog/index.html`. For every post, add this inside the `blog-list` section:

```html
<article class="blog-entry">
  <a href="posts/2026-09-23-short-post-title.html">
    <h2>Your post title</h2>
    <p>The first sentence of your post.</p>
  </a>
</article>
```

Put the newest post first. The three trailing dots are added automatically by
the stylesheet, so do not type them into the sentence yourself.

## 4. Preview and publish

Preview the site from the repository root:

```sh
python3 -m http.server 8000
```

Then open `http://localhost:8000/blog/`. When everything looks right, commit
and push the changes to `main`; GitHub Pages will publish them automatically.
