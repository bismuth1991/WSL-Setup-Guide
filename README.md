## NodeJS & NPM

```bash
# download and run the official install script
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.6/install.sh | bash

# update your terminal config (you will now have access to the nvm command)
source ~/.bashrc

# install a stable version of node (check for stable version at https://nodejs.org/en/)
nvm install 10.15.0

# set version 10.15.0 as default version
nvm use 10.15.0

# verify install/config
which node # => /Users/username/.nvm/versions/node/v10.15.0/bin/node
```

## Ruby & Rails
```bash
# install dependencies
sudo apt-get update

sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common libffi-dev

# install rbenv & ruby-build
cd
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL

# install ruby (check for latest stable version at https://www.ruby-lang.org/en/downloads/)
rbenv install 2.6.0
rbenv global 2.6.0
ruby -v # => should show the correct version

# install bundler
gem install bundler
rbenv rehash

# install Rails (check for latest version at https://rubygems.org/gems/rails)
gem install rails -v 5.2.2
rbenv rehash
rails -v # => should show the correct version
```

## PostgreSQL
+ Download and install PostgreSQL for Windows from here, don't forget to create a Desktop shortcut  
https://www.postgresql.org/download/windows/  

+ Then in your terminal, install client package and dependencies for rails...

```bash
sudo apt-get install postgresql-client libpq-dev
```

## Connecting to PosgreSQL from Rails
+ Run PosgreSQL from the shortcut in Desktop, or look for PGAdmin

+ Then in your terminal...

```bash
rails new myapp -d postgresql
cd myapp
```

+ Open the folder with your code editor of choice

+ Modify your config/database.yml

```ruby
development:
  <<: *default
  database: myapp_development
  host: localhost
  port: 5432 # or 5433, or whatever port number you chose when installing postgres
  username: postgres
  password: mypassword #you should be prompted to create a password when installing postgres
  

  ### NOTE: please don't use your username and password for porduction, use ENV variables instead
```

```bash
# You should be able to run this is your terminal
bundle exec rails db:create
```

## Misc.
+ [Set up VSCode](https://youtu.be/Zi0eofqAkXU?t=1508)

+ Install Heroku CLI 
```bash
curl https://cli-assets.heroku.com/install.sh | sh
```
