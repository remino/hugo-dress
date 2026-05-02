# hugo-dress

The little dress for Hugo

By Rémino Rem  
<https://remino.net/>

[Code Repo](https://github.com/remino/hugo-dress)

---

## Minimal Hugo theme for semantic HTML

**<mark>hugo-dress</mark>** is a small Hugo theme built around
[_dress.css_](https://remino.net/dress.css/). It provides plain, semantic
templates and lets the stylesheet do the visual work.

The theme stays deliberately bare: page structure, navigation, language links,
and optional site CSS. Section-specific behavior such as shortcodes,
pagination, taxonomies, search, and custom front matter display belongs in the
host site as Hugo layout overrides.

---

<!-- mtoc-start -->

- [Features](#features)
- [Installation](#installation)
    - [Theme directory](#theme-directory)
    - [Hugo module](#hugo-module)
- [Usage](#usage)
    - [Logo](#logo)
    - [Favicons](#favicons)
    - [Footer menu](#footer-menu)
    - [Custom CSS](#custom-css)
    - [Layout overrides](#layout-overrides)
- [Development](#development)
- [Licence](#licence)

<!-- mtoc-end -->

---

## Features

- **Class-less** - templates use semantic HTML and rely on dress.css.
- **Small** - minimal layouts and partials.
- **Plain** - no bundled search, JavaScript, resource metadata, or taxonomy UI.
- **Customizable** - host sites can override any Hugo layout or partial.
- **Hugo-native** - works as a regular theme directory or Hugo module.
- **Site-friendly** - ships dress.css and combines optional host
  `assets/css/custom.css` after it in the same stylesheet.

[Back to top](#)

---

## Installation

### Theme directory

Add this repository to a Hugo site under `themes/dress`, then set:

```yaml
theme: dress
```

### Hugo module

Import the module:

```sh
hugo mod get github.com/remino/hugo-dress
```

Then add it to your Hugo configuration:

```yaml
module:
    imports:
        - path: github.com/remino/hugo-dress
```

[Back to top](#)

---

## Usage

The default templates render home, list, term, and single pages with ordinary
HTML elements such as `header`, `nav`, `main`, `article`, `section`, `footer`,
lists, and definition lists.

### Logo

Set `params.dress.logo` to show a logo before the site title:

```yaml
params:
    dress:
        logo:
            src: images/logo.svg
            width: 100
            height: 100
            alt: ""
```

### Favicons

Set `params.dress.favicons` to add favicon link tags:

```yaml
params:
    dress:
        favicons:
            - href: favicon.ico
              sizes: any
            - href: favicon.svg
              type: image/svg+xml
            - rel: apple-touch-icon
              href: apple-touch-icon.png
```

### Footer menu

Use Hugo's `footer` menu for footer links:

```yaml
menu:
    footer:
        - name: Contact
          url: mailto:hello@example.com
          weight: 1
        - name: Back to top
          url: "#"
          weight: 2
```

### Custom CSS

Create `assets/css/custom.css` in the host site for site-specific styles. The
theme combines it after dress.css in the same stylesheet so local overrides win.

### Layout overrides

Use Hugo layout overrides in the host site for project-specific behavior. For
example, add `layouts/docs/list.html` in your site to paginate one section, or
add site partials to render custom front matter fields.

[Back to top](#)

---

## Development

Install dependencies:

```sh
npm install
```

Update the vendored dress.css asset:

```sh
npm run update:dress-css
```

Test the theme from a Hugo site that imports or symlinks this repository:

```sh
hugo server
```

[Back to top](#)

---

## Licence

Licensed under the ISC licence. See `LICENSE`.

[Back to top](#)
