# markdown-report


# Markdown report <img src="https://bookdown.org/yihui/rmarkdown/images/hex-rmarkdown.png" align="right" />


## Overview

tidytemplate provides a custom [pkgdown](https://pkgdown.r-lib.org)
template for core tidyverse packages (i.e. packages hosted by the
[tidyverse organisation](https://github.com/tidyverse)). Please don’t
use it for your own package.

The theme is built on top of the [paper bootswatch
theme](https://bootswatch.com/3/paper/).

## Using tidytemplate

Make sure your `_pkgdown.yaml` contains:

``` yaml
template:
  package: tidytemplate

development:
  mode: auto

home:
  strip_header: true
```

You can customise the “part of” in the header, the footer text, and add
an optional tidymodels CSS theme with template parameters:

``` yaml
template:
  package: tidytemplate
  params:
    part_of: tidymodels
    footer: ...
    theme: tidymodels
```

To work properly, `tidytemplate` requires the css files in
`inst/pkgdown/assets/`. Because of this, you should not set
`default_assets: false` in your `_pkgdown.yaml`.

``` yaml
template:
  package: tidytemplate
  # Do not do this!
  default_assets: false
```

If you deploy to github pages automatically using travis, add the
following to your `.travis.yml`:

``` yaml
r_github_packages:
  - tidyverse/tidytemplate
```

## CSS files

Three CSS files play a role in styling the site:

  - `tidyverse.css` is generated from files in `scss/` written by Robby
    Shaver. Generally you should not touch these files; Robby is the
    owner. If needed you can regenerate `tidyverse.css` by running this
    code:
    
    ``` r
    # devtools::install_github("rstudio/sass")
    library(sass)
    sass(
      sass_file("scss/tidyverse.scss"),
      output = "inst/pkgdown/assets/tidyverse.css",
      options = sass_options(output_style = "nested")
    )
    ```

  - `pkgdown.css` comes from pkgdown.

  - `tidyverse-2.css` lives in `inst/pkgdown/assets/tidyverse-2.css`.
    Generally, this is the only file you should touch if you want to
    make changes to the style of the site.

  - `tidymodels.css` is an optional CSS file written by [Desirée De
    Leon](http://desiree.rbind.io) that lives in `inst/pkgdown/assets/`.
    This file is loaded when the `theme:` parameter is used.
