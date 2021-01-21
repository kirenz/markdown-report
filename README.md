## Markdown report <img src="https://bookdown.org/yihui/rmarkdown/images/hex-rmarkdown.png" align="right" width="10%" height="10%" />

- This repo provides a custom R Markdown report template: view [HTML file](https://htmlpreview.github.io/?https://github.com/kirenz/markdown-report/blob/master/markdown-report.html) (note: this preview can't view all elements of the report). 
- To work properly, the report requires the files `style.css` and `footer.html`. 
- To learn more about the basics of R Markdown, review the [documentation](https://rmarkdown.rstudio.com) or this excellent [presentation](https://drive.google.com/file/d/1mD6qQlUft2g5oc3SGVuOUGHpE3FtStkr/view) from RStudio's Alison Hill.


## Customising

- You can customise the report by changing the `YAML` metadata in the header of the document. 
- To customise the style of the HTML including layout, colors, and fonts you can change the CSS in the file `style.css`. 
- The content of the footer can be changed in the file `footer.html` (open this file with an editor) 

YAML Metadata:

``` yaml
---
title: "Write Reports in R Markdown"
author: "Prof. Dr. Jan Kirenz, HdM Stuttgart"
output:
 html_document: 
  css: style.css # define your own css
  df_print: paged #  tables are printed as HTML tables 
  highlight: default # syntax highlighting style 
  number_sections: yes # numbering of sections
  theme: paper # style option
  fig_height: 4 # figure height
  fig_width: 8 # figure width
  toc: yes # table of content
  toc_float: 
    collapsed: false # show full toc
    smooth_scroll: true # toc scrolling behavior
  includes:
    after_body: footer.html # include footer
---
```

