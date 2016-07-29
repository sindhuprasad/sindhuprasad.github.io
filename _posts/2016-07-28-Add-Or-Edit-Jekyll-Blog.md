---
layout: post
title: How to add/edit a post in your jekyll blog?
---

This post describes how to make changes to your jekyll blog. It can be done locally, where the github pages repo is local to your machine. Or, changes can also can done directly on github. The preview feature on github while adding a post makes it very easy to verify the format before it goes live in github.io website.


###Local Development 

1. Clone your github pages repo on your local machine `git clone https://github.com/yourusername/yourusername.github.io.git`
2. Create you page under posts directory `_posts/2016-3-3-Hello-World.md`
3. Serve the site using this command jekyll serve
4. View local website at http://0.0.0.0:4000
5. Once the changes are done, use regular git commands to push the changes to github pages repo.

###Remote - Github / Thirdparty Content Editor

1. Visit `https://github.com/yourusername/yourusername.github.io/tree/master/_posts`
2. Click on Create New File button to create a new post with the same format `yyyy-mm-dd-Title.mld`
3. You can preview the page before you commit the changes.



