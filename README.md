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
basic shortcodes, and optional site CSS. Section-specific behavior such as
pagination, taxonomies, search, and custom front matter display belongs in the
host site as Hugo layout overrides.

---

<!-- mtoc-start -->

- [Features](#features)
- [Installation](#installation)
    - [Theme directory](#theme-directory)
    - [Hugo module](#hugo-module)
    - [CSS dependencies](#css-dependencies)
- [Usage](#usage)
    - [Custom CSS](#custom-css)
    - [Layout overrides](#layout-overrides)
- [Development](#development)
- [Licence](#licence)

<!-- mtoc-end -->

---

## Features

- **Class-less** - templates use semantic HTML and rely on dress.css.
- **Small** - minimal layouts, partials, and shortcodes.
- **Plain** - no bundled search, JavaScript, resource metadata, or taxonomy UI.
- **Customizable** - host sites can override any Hugo layout or partial.
- **Hugo-native** - works as a regular theme directory or Hugo module.
- **Site-friendly** - loads optional host `assets/scss/index.scss` after
  dress.css.

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

### CSS dependencies

Install the CSS build dependencies in the Hugo site:

```sh
npm add @remino/dress.css postcss postcss-cli postcss-import
```

[Back to top](#)

---

## Usage

The default templates render home, list, term, and single pages with ordinary
HTML elements such as `header`, `nav`, `main`, `article`, `section`, `footer`,
lists, and definition lists.

### Custom CSS

Create `assets/scss/index.scss` in the host site for site-specific styles. The
theme compiles it after dress.css so local overrides win.

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

Test the theme from a Hugo site that imports or symlinks this repository:

```sh
hugo server
```

[Back to top](#)

---

## Licence

Licensed under the ISC licence. See `LICENSE`.

[Back to top](#)
