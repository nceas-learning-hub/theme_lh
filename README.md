# NCEAS Learning Hub SCSS Stylesheet Extension For Quarto

This Quarto extension includes:

* a custom light and dark mode SCSS stylesheet for Quarto projects (e.g., websites, books, etc.)
* .lua filters to create custom callouts specific to the Learning Hub
* Rules are included both for easy text styling and for small quality of life improvements (e.g., increased contrast between page background color and tabset panel background, etc.). I'll update this as needed for my own projects so check back in for updates periodically!

This borrows from and is inspired by [Nick Lyon's Quarto theme extension](https://github.com/njlyon0/lyon_scss-theme).  

The custom callouts are borrowed from [https://cambiotraining.github.io/quarto-course-template/materials/02-content_guidelines.html#callout-boxes].

## Installing

```bash
quarto add nceas-learning-hub/lh_theme
```

This installs the extension under the `_extensions` directory in the course repository.

## Using in coreR

The themes included in this extension can be called in the `_quarto.yml`.  This is already set up in the `_quarto_template.yml` that is installed in the course directory when running `coreR::setup_lessons()`.

```
    theme:
       light: _extensions/nceas-learning-hub/lh_theme/lh_light.scss
       dark: _extensions/nceas-learning-hub/lh_theme/lh_dark.scss
```
