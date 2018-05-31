---
layout: post
title: "Jekyll Github pages"
---

## Goal
To setup a website using github-pages, and to test it locally.

## Reference Docs
- [Setup github pages locally](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/)
- [Setup github pages in master/docs folder](https://blog.github.com/2016-08-17-simpler-github-pages-publishing/)
- [Learn about Ruby Gems](https://guides.rubygems.org/)
- [Learn about bundler](https://bundler.io/)


## Traces and Notes

### Installing github-pages (specific version of jekyll for github)

```sh
# Use github UI to create git repo 'site-jekyll'
git clone <site-url>
cd <site>
#not-needed, use docs -- git checkout -b gh-pages
# create Gemfile which installs jekyll
gem install bundler
bundle install
git add Gemfile Gemfile.lock
```

#### About github-pages
 - Try ```github-pages --help```
 - Update github pages with ``` gem update github-pages```

### Create and test the github jekyll site:
```sh
bundle exec jekyll _3.3.0_ docs
cd docs
# In docs, edit the Gemfile to use github-pages instead of jekyll. Change title and description if you like. 
bundle exec jekyll serve -H 0.0.0.0
```

When happy, commit and push to publish 

```sh
git status
git add .
git commit -am "publish as it is now"
git push
```




### **Notes**
- bundle install failed:  
  correction: do ```sudo apt install zlig1g-dev```
- short note about gem and bundle:
  - bundle maintains specific dependencies for the specific project in file Gemfile.lock;
  - gem specifies dependencies more loosely, and provides an executable for many projects.
  - if you want to create an app, then you want to commit Gemfile.lock; otherwise not.

