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

- Navigate to your `gh-pro` branch and enter the `config.yml` file
- Create a new line that starts with `markdown:` and then type in `jeykll`
- At the bottom of the page, type a short, meaningful commit message that describes the change you made to the file. You can attribute the commit to more than one author in the `commit message`!
- If you have more than one email address associated with your GitHub account, click the email address drop-down menu and select the email address to use as the Git author email address. Only `verified` email addresses appear in this drop-down menu. If you enabled email address privacy, then `<username>@users.noreply.github.com` is the default commit author email address.
- Below the commit message fields, decide whether to add your commit to the current branch or to a new `branch`. If your current `branch` is the `default branch`, you should choose to create a new `branch` for your commit and then create a `pull request`.
- then click `Click Propose new file.`
  
Now Navigate to **Jeykll** and go to your website project! now go to `commandline` and then `plugins` and then `custom` now type `jeykll new plugin markdown lib install` and it should install! Now **Build your website** and test it!
  
### Find More Documentations [Here](https://kadedevteam.github.io/Documentations/)
