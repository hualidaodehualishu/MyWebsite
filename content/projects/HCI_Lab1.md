+++
title: "Create a blog"
date: 2023-01-30
description = "I created a personal website that contains some basic information about me and my studies. The following will show the process of creating my website."
+++

## create process

I created my personal page using Hugo. After creating a new sit, you can download the themes you like from the Hugo page according to your preferences. After initializing git with git init, run the following command to download the hugo-coder theme in the theme directory，using the submodule command.
![409561675045884_.pic.jpg](https://s2.loli.net/2023/01/30/vdtaP3rM5mF1q9w.jpg)
## Personal configuration and site generation
The configuration file is config.toml under quickstart in the root directory of the site, and you can modify it according to your needs. The files in the exampleSite folder under the avarar theme can be used as a reference. The default posts will be stored in . /content/post. Whenever you finish writing a post, run the hugo command and Hugo will automatically generate a static site in the public folder, and we just need to post the contents of that folder on the web.

## GitHub Pages
For more information about GitHub pages, check out the official website, which consists of four steps.

Create an empty username.github.io repository with the same name as your username, without any content like readme.md. For example, my username is Mywebsite, so I created a repository called hulidaodehualishu.github.io;
Clone the repository locally
git clone https://github.com/hulidaodehualishu.github.io
Add personal website content to the repository

copy the generated website content to the repository folder
cp -rf quickstart/public/* http://hulidaodehualishu.github.io/
Synchronize the file content to the GitHub server
cd http://hulidaodehualishu.github.io
git add .
git commit -m "init the website"
git push

At this point, you can access your personal website by going to https://hulidaodehualishu.github.io.

This is how I created my blog.



