---
layout: post
title: A simple way to use jekyll plugins on GitHub Pages
tags: [jekyll,plugins,GitHub]
---

> [GitHub Pages] provide user a decent way to publish their static webpage or log. As we al know, custom plugins are disabled when the `safe` mode is on. Here, I would like to illustrate a simple to allow jekyll plugins in the [GitHub Pages]. 

[GitHub Pages]: http://pages.github.com/ 

The solution is as follows: build a `master` branch with compiled website and `source` branch with all our website sources. 

### Step1: Build a github repository for the webpages

Here, I illustrate an example to publish a webpage using the special repository dedicated to the Github pages files. This special repository mush be named like `username.github.io`.

### Step2: Prepare the repository
Creat a `source` branch in our repository to store all the webpages sources.
    $ git checkout -b source master
    $ git push -u origin source
Make the `source` branch _default_ on your Github.

### Step3: Rakefile to publish webpages automatically

Now, you can push your compiled `sources` into the master branch to pulish. Use the Rakefile as follows will automatically publish your webpages.

{%highlight ruby%}

    require 'rubygems'
    require 'rake'
    require 'rdoc'
    require 'date'
    require 'yaml'
    require 'tmpdir'
    require 'jekyll'

    desc "Generate blog files"
    task :generate do
      Jekyll::Site.new(Jekyll.configuration({
        "source"      => ".",
        "destination" => "_site"
      })).process
    end


    desc "Generate and publish blog to gh-pages"
    task :publish => [:generate] do
      Dir.mktmpdir do |tmp|
        system "mv _site/* #{tmp}"
        system "git checkout -B master"
        system "rm -rf *"
        system "mv #{tmp}/* ."
        message = "Site updated at #{Time.now.utc}"
        system "git add ."
        system "git commit -am #{message.shellescape}"
        system "git push origin master --force"
        system "git checkout master"
        system "echo yolo"
      end
    end

task :default => :publish
{%endhighlight%}
Then, you can run `rake publish` to compile and publish your website to Github pages.