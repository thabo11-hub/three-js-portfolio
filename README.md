# Eldridge · portfolio

Portfolio and CV of **Thabo Eldridge Sodi**, Platform Engineer at Absa Group in Johannesburg.

It's a single page built with three.js. Every project is a star in a 3D sky that rearranges itself as you scroll. The page is styled like an anime title card, with a few game touches.

## What's on the page

- Experience timeline, certifications and 27 verified Credly badges
- Three case studies, 13 live projects, selected work and more projects
- 49 technologies, each linked to the projects that use it
- Public GitHub stats
- A contact form that sends messages to my inbox
- Explore mode: drag, pinch or scroll to fly around the sky. Press **E** to open it and **Esc** to close it.
- A dark night theme and a light theme that looks like a printed manga page

## Run it locally

The whole site is one static file, `index.html`. Open it in a browser, or serve the folder:

```sh
npx serve .
# or
python3 -m http.server 8000
```

three.js r128 loads from cdnjs and the fonts load from Google Fonts, so you need an internet connection.

## Deploy

There is no build step. Publish the repository root on any static host, such as GitHub Pages, Vercel or Netlify.

## Contact form

Messages go through [FormSubmit](https://formsubmit.co) to the address in `CONFIG.email`, so there's no backend to run.

1. Deploy the site, then send yourself a test message from the form.
2. FormSubmit emails you an activation link. Click it, or the form won't deliver messages.
3. Optional: FormSubmit also sends a random string you can use instead of your address. Put `https://formsubmit.co/ajax/<that string>` in `CONFIG.formEndpoint`.

If a message can't be sent, the form keeps the visitor's text and shows your address so they can email it instead. The claude.ai copy of the page can't send email, so there the form copies the message for the visitor to paste into an email.

## Editing content

All the content lives in the first `<script>` block of `index.html`:

| Data | What it holds |
| --- | --- |
| `CONFIG` | Name, headline, email, links, location, contact form endpoint |
| `EXPERIENCE`, `CERTS`, `BADGES`, `EDUCATION` | The CV. Badge ids are Credly records (`credly.com/badges/<id>`) |
| `PROJECTS` | Every project. `tier: 'case'` makes a case study and `tier: 'featured'` a highlight. `scope` (2 to 10) sets the star size and the LV tag |
| `LIVE` | Hosted links shown under Live projects |
| `TECH_GROUPS`, `ALSO` | Technologies |
| `GITHUB` | Profile stats |

Colours and fonts are CSS custom properties at the top of the `<style>` block, one set for each theme.

## Built with

- three.js r128 (WebGL points and custom shaders)
- Plain JavaScript, HTML and CSS
- Fonts: Dela Gothic One, Zen Kaku Gothic New and IBM Plex Mono, all from Google Fonts under the SIL Open Font License

Without WebGL, it falls back to a plain page. It also respects the reduced-motion setting.

## Note on live links

Some live projects are claude.ai artifacts. Visitors can only open them once each one is shared from its Share menu.
