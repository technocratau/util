Setting up the Technocrat shell utilities
=========================================
To start making use of the included utilities simply clone this repo, and add the following to your `~/.bash_profile` file.
```
source /path/to/util/shell/bash_profile
```
For these shell utilities to work you must setup Rbenv and Bundler as explained below.

Setting up Rbenv and Bundler
============================
Rbenv is a tool which allows you to have multiple versions of ruby installed on the same computer. Bundler is a tool for managing sets of gems for your projects.
 - rbenv https://github.com/sstephenson/rbenv
 - bundler http://bundler.io

Make sure rvm is not installed:
-------------------------------
Rbenv is incompatible with rvm, so you must make sure that rvm is not installed in order to use rbenv. To uninstall rvm, run the following:
```
rvm implode
```

Install rbenv
-------------
On mac, the recommended way to install rbenv is using homebrew as follows. For alternative installation instructions see https://github.com/sstephenson/rbenv.
```
brew update
brew install rbenv
brew install ruby-build
exec $SHELL -l
```

Install ruby
------------
You can see the current version of ruby with `ruby -v`, or install a different version of ruby. `rbenv install -l` shows you all the versions you can install:
```
# Install a different version of ruby.
rbenv install 1.9.3-p448
rbenv rehash
exec $SHELL -l
```

Now you have a simple way to switch between different versions of ruby with `rbenv global 1.9.3-p448`, however it won't usually be necessary to manually switch versions, since each project can specify a version to use for ruby.

Install bundler
---------------
Install the latest version of bundler as follows. Bundler is a gem which is repsonsible for ensuring that all the correctly versioned gems which are required for a project are available (eg. compass, gem etc).
```
gem install bundler
# If you don't run the below, then the `bundle` command will not be available until you open a new bash prompt.
exec $SHELL -l
```

Install gems with bundler
-------------------------
To install the gems for a project with Bundler you need to change into a directory which contains a Gemfile and/or Gemfile.lock, and run the `bundle` command (NOT `bundler`).
```
cd /path/to/directory-containing-Gemfile
bundle
```
