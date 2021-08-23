## Errors/Troubleshooting!

### About Jekyll build errors
Sometimes, GitHub Pages will not attempt to build your site after you push changes to your site's publishing source.

- The person who pushed the changes hasn't verified their email address. For more information, see "Verifying your email address."
- You're pushing with a deploy key. If you want to automate pushes to your site's repository, you can set up a machine user instead. For more information, see "Managing deploy keys."
- You're using a CI service that isn't configured to build your publishing source. For example, Travis CI won't build the `gh-pages` branch unless you add the branch to a safe list. For more information, see "Customizing the build" on Travis CI, or your CI service's documentation.

If Jekyll does attempt to build your site and encounters an error, you will receive a build error message. There are two main types of Jekyll build error messages.

- A "Page build warning" message means your build completed successfully, but you may need to make changes to prevent future problems.
- A "Page build failed" message means your build failed to complete. If Jekyll is able to detect a reason for the failure, you'll see a descriptive error message.
For more information about troubleshooting build errors, see "Troubleshooting Jekyll build errors for GitHub Pages sites."

### Viewing Jekyll build error messages
We recommend testing your site locally, which allows you to see build error messages on the command line, and addressing any build failures before pushing changes to GitHub. For more information, see "Testing your GitHub Pages site locally with Jekyll."

When you create a pull request to update your publishing source on GitHub, you can see build error messages on the Checks tab of the pull request. For more information, see "About status checks."

When you push changes to your publishing source on GitHub, GitHub Pages will attempt to build your site. If the build fails, you'll receive an email at your primary email address. You'll also receive emails for build warnings.

You can see build failures (but not build warnings) for your site on GitHub in the Settings tab of your site's repository.

You can configure a third-party service, such as Travis CI, to display error messages after each commit.


- If you haven't already, add a file called Gemfile in the root of your publishing source, with the following content:
```
source `https://rubygems.org`
gem `github-pages`
```
- Configure your site's repository for the testing service of your choice. For example, to use Travis CI, add a file named .travis.yml in the root of your publishing source, with the following content:
```
language: ruby
rvm:
  - 2.3
script: "bundle exec jekyll build"
```
You may need to activate your repository with the third-party testing service. For more information, see your testing service's documentation.

## Troubleshooting

### Troubleshooting build errors
If Jekyll encounters an error building your GitHub Pages site locally or on GitHub, you can use error messages to troubleshoot. For more information about error messages and how to view them!

If you received a generic error message, check for common issues.

- You're using unsupported plugins. For more information, see "About GitHub Pages and Jekyll."
- Your repository has exceeded our repository size limits. For more information, see "What is my disk quota?"
- You changed the source setting in your _config.yml file. GitHub Pages overrides this setting during the build process.
- A filename in your publishing source contains a colon (:) which is not supported.

If you received a specific error message, review the troubleshooting information for the error message below.

After you've fixed any errors, push the changes to your site's publishing source to trigger another build on GitHub.

### Config file error
This error means that your site failed to build because the _config.yml file contains syntax errors.

To troubleshoot, make sure that your `_config.yml` file follows these rules:

- Use spaces instead of tabs.
- Include a space after the : for each key value pair, like timezone: Africa/Nairobi.
- Use only UTF-8 characters.
- Quote any special characters, such as :, like title: "my awesome site: an adventure in parse errors".
- For multi-line values, use | to create newlines and > to ignore newlines.

To identify any errors, you can copy and paste the contents of your YAML file into a YAML linter, such as `YAML Validator.`

### Date is not a valid datetime
This error means that one of the pages on your site includes an invalid datetime.

To troubleshoot, search the file in the error message and the file's layouts for calls to any date-related Liquid filters. Make sure that any variables passed into date-related Liquid filters have values in all cases and never pass nil or "".

### File does not exist in includes directory
This error means that your code references a file that doesn't exist in your _includes directory.

To troubleshoot, search the file in the error message for include to see where you've referenced other files, such as `{% include example_header.html %}`. If any of the files you've referenced aren't in the `_includes directory`, copy or move the files into the `_includes directory.`

### File is a symlink
This error means that your code references a symlinked file that does not exist in the publishing source for your site.

To troubleshoot, search the file in the error message for include to see where you've referenced other files, such as `{% include example_header.html %}.` If any of the files you've referenced are symlinked, copy or move the files into the `_includes directory.`

This error means that you used non-Latin characters, like 日本語, without telling the computer to expect these symbols.

To troubleshoot, force UTF-8 encoding by adding the following line to your `_config.yml` file:
```
encoding: UTF-8
```

### Invalid highlighter language
This error means that you specified any syntax highlighter other than Rouge or Pygments in your configuration file.

To troubleshoot, update your `_config.yml` file to specify `Rouge` or `Pygments.` For more information!

### Invalid post date
This error means that a post on your site contains an invalid date in the filename or `YAML` front matter.

To troubleshoot, make sure all dates are formatted as `YYYY-MM-DD HH:MM:SS` for UTC and are actual calendar dates. To specify a time zone with an offset from UTC, use the format `YYYY-MM-DD HH:MM:SS +/-TTTT`, like `2014-04-18 11:30:00 +0800.`

If you specify a date format in your `_config.yml file`, make sure the format is correct.

### Invalid Sass or SCSS
This error means your repository contains a Sass or SCSS file with invalid content.

To troubleshoot, review the line number included in the error message for invalid Sass or SCSS. To help prevent future errors, install a Sass or SCSS linter for your favorite text editor.

### Invalid submodule
This error means that your repository includes a submodule that hasn't been properly initialized.

To troubleshoot, first decide if you actually want to use a submodule, which is a Git project inside a Git project; submodules are sometimes created accidentally.

If you don't want to use a submodule, remove the submodule, replacing PATH-TO-SUBMODULE with the path to the submodule:

```
$ git submodule deinit PATH-TO-SUBMODULE
$ git rm PATH-TO-SUBMODULE
$ git commit -m "Remove submodule"
$ rm -rf .git/modules/PATH-TO-SUBMODULE
```

If do you want to use the submodule, make sure you use `https://` when referencing the submodule `(not http://)` and that the submodule is in a public repository.

Invalid YAML in data file
This error means that one of more files in the _data folder contains invalid YAML.

To troubleshoot, make sure the YAML files in your _data folder follow these rules:
```
Use spaces instead of tabs.
Include a space after the : for each key value pair, like timezone: Africa/Nairobi.
Use only UTF-8 characters.
Quote any special characters, such as :, like title: "my awesome site: an adventure in parse errors".
For multi-line values, use | to create newlines and > to ignore newlines.
```
To identify any errors, you can copy and paste the contents of your `YAML` file into a `YAML` linter, such as `YAML Validator.`

For more information about Jekyll data files, see "Data Files" in the Jekyll documentation.

### Markdown errors
This error means that your repository contains Markdown errors.

To troubleshoot, make sure you are using a supported Markdown processor. 

Then, make sure the file in the error message uses valid Markdown syntax. For more information, see "Markdown: Syntax" on Daring Fireball.

Missing submodule
This error means that your repository includes a submodule that doesn't exist or hasn't been properly initialized.

To troubleshoot, first decide if you actually want to use a submodule, which is a Git project inside a Git project; submodules are sometimes created accidentally.

If you don't want to use a submodule, remove the submodule, replacing `PATH-TO-SUBMODULE` with the path to the submodule:
```
$ git submodule deinit PATH-TO-SUBMODULE
$ git rm PATH-TO-SUBMODULE
$ git commit -m "Remove submodule"
$ rm -rf .git/modules/PATH-TO-SUBMODULE
```
If you do want to use a submodule, initialize the submodule. For more information, see "Git Tools - Submodules" in the Pro Git book.

### Unknown tag error
This error means that your code contains an unrecognized Liquid tag.

To troubleshoot, make sure all Liquid tags in the file in the error message match Jekyll's default variables and there are no typos in the tag names. For a list of default variables, see "Variables" in the Jekyll documentation.

Unsupported plugins are a common source of unrecognized tags. If you use an unsupported plugin in your site by generating your site locally and pushing your static files to GitHub, make sure the plugin is not introducing tags that are not in Jekyll's default variables. For a list of supported plugins, see "About GitHub Pages and Jekyll."

### Missing `.jeykll` folder
This error means that you have chosen the `.jeykll` folder on a branch as your publishing source, but there is no docs folder in the root of your repository on that branch.

To troubleshoot, if your docs folder was accidentally moved, try moving the docs folder back to the root of your repository on the branch you chose for your publishing source. If the docs folder was accidentally deleted, you can either:

- Use Git to revert or undo the deletion. For more information, see "git-revert" in the Git documentation.
- Create a new docs folder in the root of your repository on the branch you chose for your publishing source and add your site's source files to the folder. For more information, see "Creating new files."
- Change your publishing source!

### Find More Doccementations [here](https://kadedevteam.github.io/Documentations/)
