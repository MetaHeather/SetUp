
Instructions to install the following tools.

- Homebrew
- Xcode
- VS Code
- Git
- Node.js
- PostgreSQL
- MongoDB
- Python
- Django



## Homebrew

Homebrew is a package manager that we will use to install various command line tools.

Open up terminal, and paste the following command to install Homebrew. You might be prompted to install XCode Command Line Tools during the install process.

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

If you are prompted to install the XCode CLI, say yes and your homebrew installation will continue.

After the installation process, run the command `brew doctor`. If any warnings or errors are displayed, we will need to resolve them before proceeding with the rest of the install fest.

Lastly, make sure to run `brew update` to make sure you have the latest lists of available software.

## Xcode

Some other applications that we do use require some Xcode libraries. Normally, all you need is the Xcode CLI which should have already been installed when you installed Homebrew. If it didn't get installed, you can use this command:

```
xcode-select --install
```

If you need to, you can install Xcode through the App Store. (You probably don't need to.) [Link here](https://itunes.apple.com/us/app/xcode/id497799835?mt=12)


## Visual Studio Code

Download and install VS Code from [https://code.visualstudio.com/](https://code.visualstudio.com/).

**Important**: Be sure that VS Code is in your Mac's `Applications` folder.

#### Add Ability to Launch VS Code by typing `code`

1. Launch VS Code using spotlight (`command + space` - then start typing `vs c` until you see the app, then press enter).
2. Type `shift + command + P` to open the command palette.
3. Start typing `shell command` and when you see the<br>`Shell Command: Install 'code' command in PATH` command - click it!
4. Quit VS Code and Terminal.
5. Relaunch Terminal
6. You should now be able to open a folder to edit by typing `code .`

Check [this link](https://code.visualstudio.com/docs/setup/mac) for troubleshooting if you run into issues.

## Git

We can use Homebrew to install it:

```
brew install git
```

#### Github

[Github](https://github.com/) provides a way to host Git repos in the cloud. 

#### Configuring a Global git ignore

Everyone should have a global **git ignore** file so that you don???t have to worry about making the appropriate entries in a project???s git ignore.

First, create the file:  `touch ~/.gitignore_global`

Next, configure git to use this file:  `git config --global core.excludesfile ~/.gitignore_global`

Finally, lets put some good stuff in there:

```sh
# This is a list of rules for ignoring files in every Git repositories on your computer.
# See https://help.github.com/articles/ignoring-files

# Compiled source #
###################
*.class
*.com
*.dll
*.exe
*.o
*.so

# Packages #
############
# it's better to unpack these files and commit the raw source
# git has its own built in compression methods
*.7z
*.dmg
*.gz
*.iso
*.jar
*.rar
*.tar
*.zip

# Logs and databases #
######################
*.log

# OS generated files #
######################
._*
.DS_Store
.DS_Store?
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

# Testing #
###########
.rspec
capybara-*.html
coverage
pickle-email-*.html
rerun.txt
spec/reports
spec/tmp
test/tmp
test/version_tmp

# node #
########
node_modules

# Rails #
#########
**.orig
*.rbc
*.sassc
.project
.rvmrc
.sass-cache
/.bundle
/db/*.sqlite3
/log/*
/public/system/*
/tmp/*
/vendor/bundle


# Ruby #
########
*.gem
*.rbc
.bundle
.config
.yardoc
_yardoc
doc/
InstalledFiles
lib/bundler/man
pkg
rdoc
tmp

# for a library or gem, you might want to ignore these files since the code is
# intended to run in multiple environments; otherwise, check them in:
# Gemfile.lock
# .ruby-version
# .ruby-gemset

# CTags #
#########
tags

# Env #
#######
.env

# Python #
#######
*.pyc
__pycache__/
```

## Node.js

Node is a JavaScript engine for the backend. We use it to power our web servers and connect to our databases.

```
brew install node
```

Verify the installation afterwards by running:

```
node -v
npm -v
```

The above commands should display versions without any errors. To verify that all the required permissions are set correctly, try to install a package such as the useful _nodemon_ globally:

```
npm install -g nodemon
```

## PostgreSQL

Install the **PostgreSQL** database management system (DBMS) using Homebrew with this command:

```
brew install postgresql
```

After Postgres is installed run this command:

```
brew services start postgresql
```
 
Followed by this command to test the install by creating a new database named the same as the current system user:
 
```
createdb
```

## Installing MongoDB

Install **MongoDB** using Homebrew with this command:

```
brew install mongodb
```

Now create the directory where your MongoDB data will be stored:

```
sudo mkdir -p /data/db
```

Be sure you include the leading slash in front of `/data/db`.

Now let's get your username:

```
whoami
```

Grant permission to your data directory:

```
sudo chown -R <your username here> /data/db
```
Or
```
sudo chown -R $(whoami) /data/db
```

### Testing the MongoDB server

You start the Mongo database server with the following command:
```
mongod
```

Press `control-c` to stop the server.

If you prefer not to have to start/stop MongoDB while working with it in class, you can run this command to ensure the MongoDB engine is running at all times:

```
brew services start mongodb
```

> Note that having the MongoDB process continuously running does consume system resources, so you may be better off manually starting/stopping MongoDB if you have an older (slower) computer.

## Installing Python 3

Brew is also used to install Python 3. (Python 2 is already installed on your Mac.)

Install **Python** using Homebrew with this command: `brew install python`. 

You can test the installation by running `python3 --version`.

Python 3's package manager, `pip3` should have automatically been installed with Python 3.  Test that it was installed by running `pip3 --version`.


## Installing Django

We will use `pip3` to install Django, a robust web framework for Python. We will be installing the latest version (2.x.x):

```
pip3 install Django
```

