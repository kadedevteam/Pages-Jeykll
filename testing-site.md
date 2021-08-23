## Testing Site with Jeykll

### Building your site locally
Changes to your site are published automatically when the changes are merged into your site's publishing source. If you want to preview your changes first, you can make the changes locally instead of on GitHub. Then, test your site locally.

### Prerequisites
Before you can use Jekyll to test a site, you must:

- Install Jekyll. (should be done)
    - Create a Jekyll site. (Should also be done!)
- This SHOULD be done as this was stated in previouse documentations!

### Building your site locally
Open Your Jeykll Project
Navigate to the publishing source for your site. (AKA YOUR **GITHUB** REPSORITY FOR THE SITE)
and open up a code workflow in `actions` and open the `commandline`, more info on that [here]()
- Run bundle install.
- Run your Jekyll site locally.
```
$ bundle exec jekyll serve
> Configuration file: /Users/octocat/my-site/_config.yml
>            Source: /Users/octocat/my-site
>       Destination: /Users/octocat/my-site/_site
> Incremental build: disabled. Enable with --incremental
>      Generating...
>                    done in 0.309 seconds.
> Auto-regeneration: enabled for '/Users/octocat/my-site'
> Configuration file: /Users/octocat/my-site/_config.yml
>    Server address: http://127.0.0.1:4000/
>  Server running... press ctrl-c to stop.
```
To preview your site, in your web browser, navigate to ``http://localhost:4000.`` in actions!

### Updating the Website
Jekyll is an active open source project that is updated frequently. If the github-pages gem on your computer is out of date with the github-pages gem on the GitHub Pages server, your site may look different when built locally than when published on GitHub. To avoid this, regularly update the github-pages gem on your computer.

- Open Git Bash.
Now Run
```
> update local site
> jeykll run build
```

### For More Doccumentations Check them out [here](https://kadedevteam.github.io/Documentations/)
