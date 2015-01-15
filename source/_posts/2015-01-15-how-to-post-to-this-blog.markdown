---
layout: post
title: "How to post to this blog"
date: 2015-01-13 21:39:49 +0800
comments: true
categories: 
sharing: true
---

In this repo besides master there's a branch called 'source'. Everytime when you run `rake gen_deploy` it will push the latest contents to the master. So keep in mind **Never push to the master!**

##Prepare 
- Run command `git clone git@github.com:ThoughtWorks-China-QA/thoughtworks-china-qa.github.io.git`
- Enter the repo `cd thoughtworks-china-qa.github.io`
- Run `git status` and make sure that you are on source branch. All of our changes will be pushed to source insteand of master
- Run `rake setup_github_pages` and input our repo: 'git@github.com:ThoughtWorks-China-QA/thoughtworks-china-qa.github.io.git'

##New post
- Run command `rake new post` and then enter you post's title. It will generate a new markdown file for you under `source/_posts`
- When you open this file you will first see the following content:

	   ---
       layout: post

       title: "How to post to this blog"

       date: 2015-01-15 21:39:49 +0800

       comments: true

       categories:

       ---
Add your content below this paragraph and save it
- Run `rake generate`
- Now you can run `rake preview` to preview your blog. Just open [http://localhost:4000/](http://localhost:4000/)
- When you finish editing please run `rake deploy` it will push your changes to master automatically
- Last step please run these one by one

      `git add .`
 
      `git commit -m 'Why and what you've done. - Name'`
  
      `git push`
