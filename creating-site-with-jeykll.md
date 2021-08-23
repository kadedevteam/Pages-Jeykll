## Creating Site With Jeykll
### You need to have a jeykll account linked to your GitHub Account for this step!

### Getting Started
Lets start by downloading jeykll-engine to get started!

Open your `commandline` and type all of this! to save this to make it importable to jeykll!
```
jekyll-coffeescript
jekyll-default-layout
jekyll-gist
jekyll-github-metadata
jekyll-optional-front-matter
jekyll-paginate
jekyll-readme-index
jekyll-titles-from-headings
jekyll-relative-links
```

Once your done open the offical [jeykll-engine web!]() and create a new project!

### Making Site

In the `Creating Project` Page, select `import` and import the source code! Then click `Create Jeykll Domain`. 

#### Syntax highlighting
To make your site easier to read, code snippets are highlighted on GitHub Pages sites the same way they're highlighted on GitHub. For more information about syntax highlighting on GitHub, see "Creating and highlighting code blocks."

By default, code blocks on your site will be highlighted by Jekyll. Jekyll uses the Rouge highlighter, which is compatible with Pygments. If you specify Pygments in your _config.yml file, Rouge will be used instead. Jekyll cannot use any other syntax highlighter, and you'll get a page build warning if you specify another syntax highlighter in your _config.yml file. For more information, see "About Jekyll build errors for GitHub Pages sites."

If you want to use another highlighter, such as highlight.js, you must disable Jekyll's syntax highlighting by updating your project's `_config.yml` file.
```
kramdown:
  syntax_highlighter_opts:
    disable : true
If your theme doesn't include CSS for syntax highlighting, you can generate GitHub's syntax highlighting CSS and add it to your project's style.css file.
```
`$ rougify style github > style.css`

While exploring your site, you will see that `links`, `headers`, and `bold/italic` text are just as they are "###" whatever text! thats beacause [GitHub Markdown]() is **NOT** built in or included with jeykll! you will have to install this yourself! you can find a full guide about that here: [Adding Github Markdown]()

### Find More Documentations [Here](https://kadedevteam.github.io/Documentations/) 
