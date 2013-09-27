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
echo -e 'export RBENV_ROOT=/usr/local/var/rbenv\nif which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.bash_profile
exec $SHELL -l
```

Install ruby
------------
You can see the current version of ruby with ```ruby -v```, or install a different version of ruby. ```rbenv install -l``` shows you all the versions you can install:
```
# Install a different version of ruby.
rbenv install 1.9.3-p448
rbenv rehash
exec $SHELL -l
```

Install bundler
---------------
Install the latest version of bundler as follows:
```
gem install bundler
exec $SHELL -l
```

Install gems with bundler
-------------------------
To install gems with Bundler you need to change into a directory which contains a Gemfile and/or Gemfile.lock.
```
cd /path/to/directory-containing-Gemfile
bundle
```
