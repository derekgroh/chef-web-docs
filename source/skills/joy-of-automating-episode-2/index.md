---
title: 'Episode 2: Scripts to Recipes with Python, Pip, and Django'
description: 'Converting the application installation and configuration instructions into tested recipes. How to Install Django from multiple sources: packages; pip; and virtualenv.'
order: 2
keywords: training, videos, screencasts
category: 'joy-of-automating'
layout: skills-topic
sections: []
icon: video.png
---

<iframe width="877" height="493" src="https://www.youtube.com/embed/vEfMLejGhS4?list=PL11cZfNdwNyORJfIYA8t07PRMchyDXIjq" frameborder="0" allowfullscreen></iframe>
<p/>

## Description

In this episode we focused on converting the installation of Django into tested recipes. We explored installing Django from multiple sources: packages; pip; and through virtualenv. Which lead us into writing integration tests and unit tests for the various recipes, defining multiple test kitchen suites, and git branch workflow. Near the end we started to define a custom resource within the cookbook to handle our requests to install packages through pip.

## Activity

In this episode we focus on taking the manual installation instructions found in [this tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-the-django-web-framework-on-ubuntu-14-04) and create a recipe that does the work for us.

* [How to Install The Django Web Framework](https://www.digitalocean.com/community/tutorials/how-to-install-the-django-web-framework-on-ubuntu-14-04)

The completed exercise can be found here: [https://github.com/chef-training/django](https://github.com/chef-training/django)

## Resources

* [chef (executable)](https://docs.chef.io/ctl_chef.html): [generate cookbook](https://docs.chef.io/ctl_chef.html#chef-generate-cookbook); [generate recipe](https://docs.chef.io/ctl_chef.html#chef-generate-recipe); [exec](https://docs.chef.io/ctl_chef.html#chef-exec)
* [kitchen (executable)](https://docs.chef.io/ctl_kitchen.html): [list](https://docs.chef.io/ctl_kitchen.html#kitchen-list);  [destroy](https://docs.chef.io/ctl_kitchen.html#kitchen-destroy); [create](https://docs.chef.io/ctl_kitchen.html#kitchen-create); and [verify](https://docs.chef.io/ctl_kitchen.html#kitchen-verify)
* [Atom commands](http://flight-manual.atom.io/): [Fuzzy Find](http://flight-manual.atom.io/getting-started/sections/atom-basics/); [Toggle Tree View](http://flight-manual.atom.io/getting-started/sections/atom-basics/); and [Panes / Split Window](http://flight-manual.atom.io/using-atom/sections/panes/)
* [Test Kitchen Configuration File](https://docs.chef.io/config_yml_kitchen.html)
* [git](https://git-scm.com): [status](https://git-scm.com/docs/git-status); [add](https://git-scm.com/docs/git-add); [commit](https://git-scm.com/docs/git-commit); [checkout](https://git-scm.com/docs/git-checkout); [clean](https://git-scm.com/docs/git-clean); [reset](https://git-scm.com/docs/git-reset); [branch](https://git-scm.com/docs/git-branch); [merge](https://git-scm.com/docs/git-merge); [diff](https://git-scm.com/docs/git-diff); and [push](https://git-scm.com/docs/git-push)
* [hub](https://hub.github.com/): [create](https://hub.github.com/hub.1.html) and [browse](https://hub.github.com/hub.1.html).
* [GitHub](https://help.github.com/): [pull requests](https://help.github.com/articles/using-pull-requests/)
* [Linux commands](http://www.mediacollege.com/linux/command/linux-command.html): [&&](http://stackoverflow.com/questions/4510640/command-line-what-is-the-purpose-of) and [cp -R](http://www.mediacollege.com/cgi-bin/man/page.cgi?topic=cp)
* [Chef Resources](https://docs.chef.io/resources.html): [package](https://docs.chef.io/resource_package.html); and [execute](https://docs.chef.io/resource_execute.html)
* [Recipe DSL](https://docs.chef.io/dsl_recipe.html): [include_recipe](https://docs.chef.io/dsl_recipe.html#include-recipes)
* [ServerSpec](http://serverspec.org/): [command](http://serverspec.org/resource_types.html#command).
* [ChefSpec](https://github.com/sethvargo/chefspec): [install_package](https://github.com/sethvargo/chefspec/tree/master/examples/package) and [run_execute](https://github.com/sethvargo/chefspec/tree/master/examples/execute)
* [RSpec](https://relishapp.com/rspec): [it](https://relishapp.com/rspec/rspec-core/v/3-4/docs/example-groups/basic-structure-describe-it); [pending examples](https://relishapp.com/rspec/rspec-core/v/3-4/docs/pending-and-skipped-examples/pending-examples); and [--init](https://relishapp.com/rspec/rspec-core/v/3-4/docs/command-line/init-option)

## Further activities

When you are done with the initial implementation we encourage you to challenge yourself by:

### Another installation

We walked through several installations. As an exercise walk through the final installation of [installing Django through git](https://www.digitalocean.com/community/tutorials/how-to-install-the-django-web-framework-on-ubuntu-14-04#development-version-install-through-git). You will need the [git](https://docs.chef.io/resource_git.html) resource.

### Custom resource

We started to write the [custom resource](https://docs.chef.io/custom_resources.html): `pip`. Finish it.

* Replace the hard-coded installation of Django with a [property](https://docs.chef.io/custom_resources.html#define-properties)
* Set that name_property to true for the property so it defaults to using the name of the resource
* Set the install action as the default action

Installing Django through git uses a specific pip flag. Provide support for it by:

* Defining a new attribute to specify a source location
* Within pip's install action choose whether to include that flag if the source attribute contains a value