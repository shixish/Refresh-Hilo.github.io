Refresh Hilo
============
Welcome to the [members site](http://www.refresh-hilo.org) repo, this repo is avalible to all members of Refreash-Hilo. Please modify with care, be respectful of your fellow members and **always remember to have fun, learn and share**. If you would like access send an email to Edward Meehan with your github username.

##Project Details
This [site](http://www.refresh-hilo.org) is built with [Jekyll](http://jekyllrb.com/) and hosted with [GitHub Pages](https://pages.github.com/).

###Dependencies
Please try to limit external dependencies and only use what resources come with the default Jekyll installation. Currently you can use [SASS](http://sass-lang.com) and [Coffescript](http://coffeescript.org) with the default Jekyll installation.

##Projet Workflow
Since we are using GIT, this part is easy. You may freely work in the *develop* branch if you're doing small changes. If you plan on doing larger changes that modify the project globally you should work in a custom branch and consult your fellow members before merging into the *develop* branch.

###Branches
**master** - this branch is actually a [submodule pointing to the subfolder](http://blog.blindgaenger.net/generate_github_pages_in_a_submodule.html) _site of the develop branch. Do not edit files in this branch. This location is the compiled files location for the jekyll project on the develop branch.

**develop** - this branch is your development branch. Most changes to this site should happen here. If your going to do some heavy lifting and want to backup your changes to github but are not ready to publish you should keep your changes in a custom branch

**username/custom_branch_name** - for custom branches follow the naming convention of your github user name followed by a forward slash, followed by a short name for the branch. 

##Going Live
Since we are using a submodule to point to a subfolder of the develop branch, deployment is actually easier than it sounds. All you need to do to deploy your changes is to commit any changes to the *develop* branch or merge your changes and run the [jekyll -build command](http://jekyllrb.com/docs/usage/) from the local project. After jekyll has compiled the new files into the _site directory you can then commit the changes in the submodule (master branch) and push them to GitHub.

This document is a work in progress - please help keep it updated
