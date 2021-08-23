## About GitHub Pages Pro and Jekyll
### Jeykll is a site engine! Check it out [here!](https://jekyllrb.com/)

```
NOTE: Github Pages Pro and Jeykll are in a team orginazation! for thoose who thinking we are using jeykll without permisson! you can read more at the offical jeykll "team" page
```

### About Jekyll
Jekyll is a static site generator with built-in support for GitHub Pages and a simplified build process. Jekyll takes Markdown and HTML files and creates a complete static website based on your choice of layouts. Jekyll supports Markdown and Liquid, a templating language that loads dynamic content on your site. For more information, see [Jekyll](https://jekyllrb.com/)

Jekyll is not officially supported for Windows. For more information, see "Jekyll on Windows" in the Jekyll documentation.

We recommend using Jekyll with GitHub Pages. If you prefer, you can use other static site generators or customize your own build process locally or on another server.

Configuring Jekyll in your GitHub Pages site
You can configure most Jekyll settings, such as your site's theme and plugins, by editing your _config.yml file. For more information, see "Configuration" in the Jekyll documentation.

Some configuration settings cannot be changed for GitHub Pages sites.

lsi: false
safe: true
source: [your repo's top level directory]
incremental: false
highlighter: rouge
gist:
  noscript: false
kramdown:
  math_engine: mathjax
  syntax_highlighter: rouge
By default, Jekyll doesn't build files or folders that:

are located in a folder called /node_modules or /vendor
start with _, ., or #
end with ~
are excluded by the exclude setting in your configuration file
If you want Jekyll to process any of these files, you can use the include setting in your configuration file.
