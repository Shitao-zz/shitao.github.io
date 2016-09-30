# shitao.github.io
Shitao's webpage

Welcome to my webpage: http://shitao.github.io/


# Easy way to build your own webpage

> [GitHub Pages] provide user a decent way to publish their static web pages or
> blogs. As we all know, custom plugins are disabled when the `safe` mode is on.
> Here, I would like to illustrate a simple way to allow jekyll plugins in the
> [GitHub Pages]. 

The solution is as follows: build a `master` branch with compiled website and `source` branch with all our website sources. 

### Step1: Build a [GitHub] repository for the web pages

Here, I illustrate an example to publish a web using the special repository
dedicated to the [GitHub Pages] files. This special repository mush be named as `username.github.io`.

### Step2: Prepare the repository
Create a `source` branch in our repository to store all the web pages sources.
    $ git checkout -b source master
    $ git push -u origin source
Make the `source` branch _default_ on your GitHub.

### Step3: Rakefile to publish web pages automatically

Now, you can push your compiled `sources` into the master branch to publish. Use
the Rakefile under source branch will automatically publish your web pages.




