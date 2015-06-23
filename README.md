# Setting up our Environment with Environmentalizer

Environmentalizer is a bash script written by developers at the Flatiron School to quickly and easily bootstrap a well-setup programming environment. 

You've already set up a functioning development environment in the pre-work: here we're going to be install a bunch of other stuff as well as making upgrades to what you already have.

**Read this readme carefully** before you run the install; even though this script will do everything for you, it's important to know what's being installed onto your machine.

## What You Need Before You Begin

1. Know your admin password (you'll need to enter it once when the script first runs)
2. Know your GitHub username
3. Know the email address associated with your GitHub account
4. A personal access api token for GitHub. You can create one here: [https://github.com/settings/tokens/new](https://github.com/settings/tokens/new). The name doesn't matter. You *must* select the following scopes (at least):
  * repo
  * public_repo
  * write:public_key
  * user
  * admin:public_key
  * gist
5. A freshly installed OS. What this means is that you will need to wipe your computer to achieve this. We know this is scary, but it's better anyway to have an external harddrive that is home to all photos, music, videos, etc. Do it!

## What It Sets Up

### `.bash_profile`

As you've been learning, your `.bash_profile` is a script that runs every time you open or login to your shell. It can configure environment variables, like your `PS1`, which stores your prompt, or `EDITOR`, which is the command other programs will use when they need to launch your default editor. You can also create aliases for common commands so that they are shorter to use. And finally, you can also build functions to simplify common workflows.

Environmentalizer is going to set up the [Flatiron Bash Profile](https://github.com/flatiron-school/dotfiles/blob/master/bash_profile), which includes case-insensitive auto completion, a nice prompt with git branch awareness, and many useful shortcuts.

Within that Bash Profile are comments that explain each part. **Make sure to read them!** You can always comment sections in/out to see what they do and how they effect your prompt, shell, and environment. When the script is done you can look in your Bash Profile from your `~` directory to see what's inside and play around with it.

Just remember, to activate a change in the dotfile, you must **reload your shell**. You can do that via opening a new tab or typing `source .bash_profile` (from the `~` directory).
 

### Command Line Tools

#### GCC

Most OS level programs are written in C or C++. These programs must be compiled and interpreted by a C-level compiler. The most common compiler for POSIX systems is GCC, or the GNU Compiler Collection. On OS 10.8 and below (anything before Mavericks), GCC is part of the Command Line Tools.

### Homebrew

Once GCC is installed, next Environmentalizer will install [Homebrew](http://brew.sh/). Homebrew will be our package manager, the system we use to install OS / Command Line level applications.

### Git

Environmentalizer will install the most recent version of git via Homebrew.

### SQlite3

SQLite3 is the database we're going to be primarily working with. Environmentalizer installs it via Homebrew.

### RVM and Ruby 2.1.2

Next Environmentalizer installs our ruby version manager, which you should already be familiar with from the prework.

Once RVM is installed, if you want any other version of ruby, just type:

`rvm install <version-number>`

### Editors with Package Control, Solarized Theme, and proper tab defaults

Editors' functionality can be greatly expanded via plugins called "packages." And we love the Solarized Theme because it's mathematically proven to be easy on your eyes.

### Sensible `.gitconfig`, `.gitignore`, `.gemrc`, and `.irbrc` files

1. `.gemrc` will omit installing the rdoc documentation and speed up gem installs.

2. `.irbrc` will allow you to see what methods an object you're working with has but excluding the stuff that exists on all ruby objects.

3. Read [Github GitIgnore Guide](https://help.github.com/articles/ignoring-files), so you understand what a global `.gitignore` will do.

4. There are some cool aliases setup in the `.gitconfig`, like git co for git checkout and git st for git status.

### SSH Key for GitHub 

So you don't have to enter your username and password every time you want to push up to Github.

### A simple directory structure for well-organized code

```bash
\Users\avi
  \Users\avi\Development
    \Users\avi\Development\books # for books and PDFs and Videos
    \Users\avi\Development\resources # for things like fonts or icons
    \Users\avi\Development\data # for raw SQL or Data Sources I use
    \Users\avi\Development\projects # for things that relate to large projects but aren't code
    \Users\avi\Development\code
      \Users\avi\Development\code\aviflombaum.github.io # Where that is a code project.
      \Users\avi\Development\code\flatiron\sql\homework1.sql # for a specific assignment in flatiron sql unit.
```

## Notes

1. You'll need to run this script from an account with admin status. (DO NOT prepend `sudo` to the command below.)
2. When the script first runs, you'll need to enter your admin password once.
3. During installation, Nitrous will open for a few seconds and then close automatically. **Do not close it yourself.** This step is required for some important directories to be created.

## Usage

`curl -Lo- "https://raw.githubusercontent.com/flatiron-school/environmentalizer/master/bootstrap.sh" | bash`
