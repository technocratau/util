Setting up rbenv and bundler
----------------------------
 - rbenv https://github.com/sstephenson/rbenv
 - bundler http://bundler.io

Rbenv is a tool which allows you to have multiple versions of ruby installed on the same computer. Bundler is a tool for managing sets of gems for your projects.

Make sure rvm is not installed:
-------------------------------
Rbenv is incompatible with rvm, so you must make sure that rvm is not installed in order to use rbenv. To uninstall rvm, run the following:
```
rvm implode
```

Install rbenv
-------------
On mac, the recommended way to install rbenv is as follows. For alternative installation instructions see https://github.com/sstephenson/rbenv.
```
brew update
brew install rbenv
brew install ruby-build
echo -e 'export RBENV_ROOT=/usr/local/var/rbenv\nif which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.bash_profile
exec $SHELL -l
```

Install ruby
------------
Install a version of ruby as follows:
```
# You may want to install a different version.
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
