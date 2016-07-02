I'm totally (re-)inspired with RMarkdown at useR! 2016. A lot going on
including bookdown and markdown documents. The latter making WordPress
blogging reasonable. Here is my first R Markdown generated post.

BTW, I'm putting the .Rmd's up on my [GitHub
here](https://github.com/ds4ci/DS4CI-Posts)

The trick is WordPress will optionally accept .md files as input to the
blog post edit window. To enable, follow the directions on the
[WordPress Markdown page](http://en.support.wordpress.com/markdown/).

R Markdown can produce plain markdown files with variants for different
dialects. See the [RStudio Markdown Documents
page](http://rmarkdown.rstudio.com/markdown_document_format.html)

For WordPress, the YAML output parameter should read

    output: 
      md_document:
        variant: markdown_phpextra+backtick_code_blocks

The workflow is to knit your .Rmd, then copy the generated markdown and
paste into your WordPress Blog Posts|Add|HTML tab.

There are two gotchas:

-   "Note however that if you have embedded plots or other images you’ll
    need to upload them separately and fix up their URLs to point to the
    uploaded location." (from above RStudio page)
-   WordPress does not seem to pick up .md title in its Title box. You
    will need to manually cut & paste the title.

Default RStudio Boilerplate {#default-rstudio-boilerplate}
===========================

As an example we use the RStudio boilerplate. The workflow is:

1.  RStudio: Knit the `<MyPost>.Rmd`
2.  WordPress|Dashboard|Media: Add image(s) from the `<MyPost>_files`
    folder to the WordPress Media Library.
3.  WordPress|Dashboard|Posts|Add New: Copy the md text from RStudio &
    paste into **HTML** tab.
4.  Copy title text from md to Text & delete title lines from the body.
5.  For each image placeholder pointing to R project folder:
    -   Delete image placeholder
    -   Insert
        `<img src="...File URL from media library..." alt="...whatever..." />`

6.  Don't forget to select categories and add tags.  
7.  WordPress: Publish & View Post

R Markdown {#r-markdown}
----------

This is an R Markdown document. Markdown is a simple formatting syntax
for authoring HTML, PDF, and MS Word documents. For more details on
using R Markdown see <http://rmarkdown.rstudio.com>.

When you click the **Knit** button a document will be generated that
includes both content as well as the output of any embedded R code
chunks within the document. You can embed an R code chunk like this:

``` r
summary(cars)
```

    ##      speed           dist       
    ##  Min.   : 4.0   Min.   :  2.00  
    ##  1st Qu.:12.0   1st Qu.: 26.00  
    ##  Median :15.0   Median : 36.00  
    ##  Mean   :15.4   Mean   : 42.98  
    ##  3rd Qu.:19.0   3rd Qu.: 56.00  
    ##  Max.   :25.0   Max.   :120.00

Including Plots {#including-plots}
---------------

You can also embed plots, for example:

![](WordPressPostsViaRMarkdown_files/figure-markdown_phpextra+backtick_code_blocks/pressure-1.png)

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.
