Refresh Hilo
============
Welcome to the [members site](http://www.refresh-hilo.org) repo, this repo is avalible to all members of Refresh-Hilo. Please modify with care, be respectful of your fellow members and **always remember to have fun, learn and share**. If you would like access send an email to Edward Meehan with your github username.

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

##Creating new members and events documents
We have some shell scripts to use with your Vagrant VM, now creating a new document for members or events is just a single command away. This will create the file in the proper location and also add some starter text to get you going quicker. No more copy and paste of a template.
###How to use shell scripts
After you have launched the Vagrant VM, ssh into the VM:

```
vagrant ssh
```
####Create new event document
```
new_event $date $type "$title" $location $meetupid $hangouturl
```
Replace the $arguments with the values for the event, the only required value is the date. The date must be formatted properly to work with Jekyll. Date format: YYYY-MM-DD ex: 2015-02-23. Also the $title must be in quotes if it has spaces. ex: "Meetup event title"
```
new_event 2015-02-21 meetup "New meetup event" HTE 122358 'http://hangouturl.com'
```
The file should be in the project - projectloction/_events/2015-02-21-meetup.md

####Create new member document
```
new_member $fname $lname
```
Replace $fname and $lname with your first name and last name: ex:

```
new_member Edward Meehan
```
The file should be in the project - projectlocation/_members/edward-meehan.md

##Liquid Template Notes

###Variables
To learn more about project vars [visit this page](http://jekyllrb.com/docs/variables/).
####Site Variables
Site vars are global to the project, some have default values while others values changes based on the current document. Global vars can also be added in the *_config.yml* file located in the root of the project.
* site.jquery - set version for project jQuery JS library
* site.modernizr - set version for project Modernizr JS library
* site.bootstrap - set version for project Bootstrap JS library

####Page Variables
Page vars are local to the document and the inherited template files.
* page.bodyClass - use to add a class name to the body tag of default layout for page level style controls

This document is a work in progress - please help keep it updated

##Resources

* [Jekyll](http://jekyllrb.com/)
* [Twitter Bootstrap](http://getbootstrap.com/)
* [jQuery](http://jquery.com/)
* [Modernizr](http://modernizr.com/)
* [Mono Social Icons Font](http://drinchev.github.io/monosocialiconsfont/)

##Vagrant

Use the included VagrantFile to develop without installing and configuring jekyll on your local machine.

[Vagrant is available](https://www.vagrantup.com) for Mac OS X, Windows, and Linux.


```
cd Refresh-Hilo.github.io
vagrant up
```

Finally, you can ssh into the vm and do all your Jekyll-related work in there:

```
vagrant ssh

cd /vagrant

jekyll server --force_polling  -P 8124
```

###View your modifications

Vagrant is configured to forward port 8124.

Open the following url in your web browser:

```
http://localhost:8124
```