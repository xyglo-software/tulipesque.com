# Publishing your Markdown Blog to Github Pages while being able to test locally

It's stunning how poor the documentation is for this relatively simple task. If you're
unfamiliar with Ruby and with Gems then there is a lot that is missing and/or confusing.
I'm trying to make this a little bit simpler but it will take a while to sort through
the various pages and information.

Github pages allow you to publish a Jekyll based website. But be aware that GitHub pages
only supports olders versions of Ruby and older version of Jekyll. If, you're like me, and
you want to have the same version running locally (on your M1 Mac in my case) as on GitHub
pages then please follow along.

## Documentation

Unhelpful documentation such as [the Jekyll ruby documentation here](https://jekyllrb.com/docs/github-pages/).

Helpful documentation such as [here](https://dev.to/azukacchi/setting-up-github-pages-site-with-jekyll-tutorial-1l60).


### Get the correct Ruby version

Firstly and most importantly make sure you're working to the correct version of ruby according to
what github pages can support. Installation and maintenance of ruby is not helped by the variety
of different version management tools that ruby comes with.

You can check out [this page](https://pages.github.com/versions/) to find the version of ruby you need.

What worked for me was to:

$ rbenv install ruby-2.7.4
$ rbenv init

this creates an entry in .bash_profile

richardbown@invis-think:~>ruby -v
ruby 2.6.10p210 (2022-04-12 revision 67958) [universal.arm64e-darwin23]
richardbown@invis-think:~>. .bash_profile
richardbown@invis-think:~>ruby -v
ruby 2.7.4p191 (2021-07-07 revision a21a3b7d23) [arm64-darwin23]

## Install Jekyll 

According to the docs, you'll need Jekyll 3.9.5 to match that in GitHub.

$ gem install jekyll -v 3.9.5

You might need to install a few other gems according to what is reported:

To fix a problem:

$ gem install google-protobuf -v 4.26.1

It can complains that ruby version is i correct:

$ gem install sass-embedded -v 1.63.6

## Create a New Directory for your site i.e.

$ mkdir newlblog
$ cd newblog
$ jekyll new .


## Install the "just-the-docs" theme (if you like)

For example from [here](https://dev.to/azukacchi/setting-up-github-pages-site-with-jekyll-tutorial-1l60)

$ gem install just-the-docs

Then edit the Gemfile to include this gem:

gem "just-the-docs"

then:

$ bundle install

then modify \_config.yaml to include this theme:

remote_theme: pmarsceill/just-the-docs

Then run the bundle exec to serve the site locally:

$ bundle exec jekyll serve

## Play with the theme customisations

https://just-the-docs.github.io/just-the-docs/docs/configuration/

## Push and setup on github

TBD
