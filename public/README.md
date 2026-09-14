# singhsujeet0.web.app

Personal portfolio — [singhsujeet0.web.app](https://singhsujeet0.web.app/)

Static site (HTML / SCSS / jQuery) hosted on Firebase Hosting.
Pushes to `master` deploy automatically via `.github/workflows/deploy.yml`.

## Layout

```
public/
  index.html          single page: home, about, projects, experience, contact
  style/style.scss    source of truth -> compiled to style.css
  scripts/
    index.js          nav, scroll animations, gallery filter, contact form
    modal.js          project modal content + carousel
    canvas.js         animated hero background (depends on pt.min.js)
  img/
    thumb-N.jpg       gallery card backgrounds (referenced from a SCSS @for loop)
    slides/           modal carousel images, named <project>-N.jpg
  RESUME/             resume.tex + compiled PDF
```

## Working on it

Styles are compiled, not authored, in `style.css`. After editing the SCSS:

```sh
npx sass --no-source-map public/style/style.scss public/style/style.css
```

Adding a project means touching three places: a `.mix` card in `index.html`,
an entry in `modalText` in `scripts/modal.js`, and images at
`img/thumb-N.jpg` plus `img/slides/<id>-0..2.jpg`.

## Deploy

```sh
firebase deploy --only hosting
```
