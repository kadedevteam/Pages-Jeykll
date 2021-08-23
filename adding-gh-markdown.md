## Adding GitHub Markdown!

### Installing Markdown into Jeykll Site
while exploring your site you might notice that GitHub Markdown **IS NOT** built in/installed and you have to install it manualy!

Go To the offical [GitHub Markdown]() page and download the Markdown source! 

While in the source open the `commandline` inside the `source` and type in `ghMarkdownlib <target> -jeykll` replace <target> with your repostory `git` to do this go into `page settings` and click `clone rep` and then back to the `commandline` and crtl+v to paste it! then run it!

Go Into your GitHub Repostory for your Website and head over to `actions`, and create a new workflow and call it `jeykll-markdown` and type in this:
```
> jeykll connect rep
> newplugin -jeykll
> set markdown
```

### Adding it to the Jeykll Lib!
Now that we have the plugin installed lets add it to jeykll

  
