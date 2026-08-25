# Ethical Hacking Diary

A GitHub Pages site for course homework write-ups. Each homework has its own page/URL and is written in plain Markdown — GitHub builds the site automatically on every push (Jekyll), no build step needed on your end.

## Structure

- `h1.md` ... `h8.md` — one file per homework, published at `/h1/`, `/h2/`, ... `/h8/`
- `index.md` — the home page listing all homeworks
- `_layouts/default.html` — shared page template (nav bar + footer)
- `assets/css/style.css` — all styling
- `assets/img/h1/`, `assets/img/h2/`, ... — put each homework's screenshots here (create the folder when you need it)

## Writing a homework entry

Open the relevant `hN.md` file. It already has an `a)`/`b)`/`c)` skeleton — add more `##` sections if a homework has more parts. Each `##` heading becomes a section with a divider above it.

```markdown
## a) Task title

Explanation of what you did.

![What the screenshot shows](/assets/img/h1/screenshot1.png)

## b) Task title

More explanation, maybe a code block:

​```bash
nmap -sV target.local
​```
```

Markdown supports code blocks, bullet lists, tables, blockquotes, bold/italic, and links — all standard GitHub-flavored Markdown.

## Adding pictures

1. Drop the image file into `assets/img/hN/` (make the folder if it's the first image for that homework).
2. Reference it in the Markdown with `![alt text]({{ '/assets/img/hN/filename.png' | relative_url }})` — the `relative_url` filter matters because this site is hosted at `/HackmasterDiary/`, not the domain root, so a plain `/assets/...` path will 404.

Keep filenames simple (no spaces) and images reasonably sized so pages load fast.

## Submitting a specific homework

Once the site is live, the URL to hand in for homework N is:

```
https://<your-username>.github.io/<repo-name>/hN/
```

## Publishing (one-time setup)

1. Push this repo to GitHub.
2. In the repo, go to **Settings → Pages**.
3. Under "Build and deployment", set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Save. The site builds automatically within a minute or two of each push, at `https://<your-username>.github.io/<repo-name>/`.

No local Jekyll/Ruby install is required — GitHub does the build for you. If you want to preview changes locally before pushing, install Ruby + Jekyll and run `bundle exec jekyll serve`, but it's entirely optional.
