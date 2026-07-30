# Editing your site (amirkiaml.github.io)

The live site is `index.html` — one plain HTML file. No build step, no framework. Edit it directly in the GitHub web editor (open the file → pencil icon) or any text editor, then commit.

## How it's organized

Each section (Agentic AI Work, RAG Projects, Data Analytics, podcast episodes, talks, publications, education, certificates...) is a list of self-contained blocks. Every block is preceded by an HTML comment naming it, e.g.:

```html
<!-- VoiceCaptures Voice Agent -->
<details style="...">
  <summary style="...">
    ... card content shown when closed ...
  </summary>
  <div style="...">
    ... extra content shown when the card is clicked open ...
  </div>
</details>
```

## Adding a new item (project, episode, talk, publication, etc.)

1. Find the section you want in the file (search for its heading text, e.g. "RAG Projects").
2. Copy one whole existing block in that section — from its `<!-- comment -->` down through its closing `</details>` (or `</div>`/`<a>` for simpler list rows like talks/publications).
3. Paste the copy right above the section's closing `</div>`.
4. Edit the pasted copy: title, description text, tags, and links. Leave the `style="..."` attributes as they are — that's what keeps the look consistent.

## Adding a new image

1. Upload the image file into the `uploads/` or `assets/` folder in the repo.
2. Point an `<img src="uploads/your-file.png" ...>` at it, matching the `style` of a neighboring image in that section (so sizing/cropping matches).

## Editing existing text/links

Just find the text in the file (Ctrl/Cmd+F) and change it in place — no other structure needs to move.

## Podcast episodes / rolling strips

These live inside a horizontally-scrolling row (`animation: vm-scroll ...`). The list is duplicated once in the HTML so the loop is seamless — if you add an episode, add it in **both** copies of the row, in the same position, so the seam stays invisible.
