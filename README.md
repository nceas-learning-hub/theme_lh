# NCEAS Learning Hub Themes

## General style guide

There currently exists a [Google doc describing a style guide](https://docs.google.com/document/d/1TTDdxCXuyqDoY8VaXNbnVCWrf9djwb2dww92lBGJeEo/edit?tab=t.0).
However, the colors are not consistent with usage on the NCEAS Learning Hub site,
and are not consistently used in Learning Hub slide decks.  Here I propose an update
to the LH style guide to be used in the `lhCore` package.

__Fonts:__

* Sans-serif: [Figtree](https://fonts.google.com/specimen/Figtree)
    * [Nunito](https://fonts.google.com/specimen/Nunito) is also good
    * Figtree resembles Avenir which is used throughout the current NCEAS site, including the LH page.
    * Headers: 700 weight; regular text: 400 weight.
* Serif:
    * There do not appear to be any serif fonts used on the current NCEAS site including the LH page.
    * The slide template seems to use [Arvo](https://fonts.google.com/specimen/Arvo) but it's kinda ugly? Sorry, Arvo!
* Monospaced:
    * currently left as default... suggestions?

__Colors:__

Some of these colors come from the older LH style guide, which seem to have been
chosen from colors on the hex sticker logo (or vice versa?).  Some of those colors
did not look great on the page together, so have been chosen from other sources,
including the green headers on the NCEAS LH site and colors from the viridis
color scale.  These are all included in the lh_slides.scss sheet, and are expanded
upon (i.e., lighter and darker variations for various uses) in the Quarto extension themes.

* <span style="color:black;background:#FFFFFF;font-family:monospace">#FFFFFF</span> white (pure white)
* <span style="color:white;background:#A23923;font-family:monospace">#A23923</span> red (from previous LH style guide)
* <span style="color:white;background:#DB9D26;font-family:monospace">#DB9D26</span> yellow (from previous LH style guide)
* <span style="color:white;background:#167B62;font-family:monospace">#167B62</span> green (from NCEAS LH site headers)
* <span style="color:white;background:#A1CAC0;font-family:monospace">#A1CAC0</span> light green (lightened version of previous)
* <span style="color:white;background:#00588B;font-family:monospace">#00588B</span> blue (viridis blue)
* <span style="color:white;background:#4B0055;font-family:monospace">#4B0055</span> purple (viridis purple)
* <span style="color:black;background:#F4F3EE;font-family:monospace">#F4F3EE</span> off-white (warm light gray)
* <span style="color:white;background:#BCB8B1;font-family:monospace">#BCB8B1</span> gray (medium gray)
* <span style="color:white;background:#08090A;font-family:monospace">#08090A</span> black (moderated black)

## SCSS for Quarto slides

`scss/lh_slides_style.scss` contains formatting and style information for Learning Hub slides.
Unfortunately, Quarto does not (currently) support using a URL for a theme, so the
user should place this file in the folder with the slides .qmd file.  On the bright side,
this could allow the user some flexibility if they really wanted to add some new style,
since the style guide would no longer be dependent on the online version...

## SCSS Stylesheet Extension For Quarto

This Quarto extension includes:

* a custom light and dark mode SCSS stylesheet for Quarto projects (e.g., websites, books, etc.)
* .lua filters to create custom callouts specific to the Learning Hub
* Rules are included both for easy text styling and for small quality of life improvements (e.g., increased contrast between page background color and tabset panel background, etc.). I'll update this as needed for my own projects so check back in for updates periodically!

This borrows from and is inspired by [Nick Lyon's Quarto theme extension](https://github.com/njlyon0/lyon_scss-theme).  

The custom callouts are borrowed from [https://cambiotraining.github.io/quarto-course-template/materials/02-content_guidelines.html#callout-boxes].

### Installing

```bash
quarto add nceas-learning-hub/lh_theme
```

This installs the extension under the `_extensions` directory in the course repository.

In the `{lhCore}` package, there is a function, `install_theme()`, that can do the same, in the context of `setup_course_structure(theme = 'lh')` function.

### Using 

The themes included in this extension can be called in the `_quarto.yml`.  This is already set up in the `_quarto_template.yml` that is installed in the course directory when running `lhCore::setup_lessons()`.  Note that the `theme` folder is left generic (no `lh` reference) so that other themes (e.g., `theme_adc`, `theme_delta`) can be developed without having to modify the `_quarto.yml` file.

```
    theme:
       light: _extensions/nceas-learning-hub/theme/lh_light.scss
       dark: _extensions/nceas-learning-hub/theme/lh_dark.scss
```
