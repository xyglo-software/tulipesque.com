# Publishing your Markdown Blog to Github Pages while being able to test locally

It's stunning how poor the documentation is for this relatively simple task. If you're
unfamiliar with Ruby and with Gems then there is a lot that is missing.

Github pages allow you to publish a Jekyll based website. But be aware that Githhub pages
only supports olders versions of Ruby.

Unhelpful documentation such as [here](https://jekyllrb.com/docs/github-pages/)


So first of all make sure you're working to the correct version of ruby according to what
github pages can support. Installation and maintenance of ruby is not helped by the variety
of different version management tools that ruby comes with.

What worked for me was to:

$ rbenv install ruby-2.7.4
$ rbenv init

creates an entry in .bash_profile

richardbown@invis-think:~>ruby -v
ruby 2.6.10p210 (2022-04-12 revision 67958) [universal.arm64e-darwin23]
richardbown@invis-think:~>. .bash_profile
richardbown@invis-think:~>ruby -v
ruby 2.7.4p191 (2021-07-07 revision a21a3b7d23) [arm64-darwin23]



You can check out [this page](https://pages.github.com/versions/) to find that out.

Secondly, according to your platform - install jekyll:

$ gem install jekyll

To fix a problem

$ gem install google-protobuf -v 4.26.1

It complains that ruby version is incorrect

$ gem install sass-embedded -v 1.63.6

It complains that ruby version is incorrect


3. Create new directory and cd into it and create jekyll

$ mkdir newlblog
$ cd newblog
$ jekyll new .


4. Install a theme:

For example from [here](https://dev.to/azukacchi/setting-up-github-pages-site-with-jekyll-tutorial-1l60)

$ gem install just-the-docs

Then edit the Gemfile to include this gem:

gem "just-the-docs"

then:

$ bundle install

then modify \_config.yaml to include this theme:

theme: "just-the-docs"

Then run the bundle:

$ bundle exec jekyll serve


5. Downgrade jekyll version to match that of github (3.9.5)

6. Play with the theme customisations

https://just-the-docs.github.io/just-the-docs/docs/configuration/






