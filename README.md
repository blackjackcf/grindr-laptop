Grindr-Laptop 
======

![grindr](http://www.grindr.com/wp-content/uploads/2015/10/grindr-logo.png)

Laptop is a script to set up a Mac OS X or Linux laptop with the basic development tools for the Grindr Services Team.

Requirements
------------

We support:

* OS X Mavericks (10.9)
* OS X Yosemite (10.10)
* OS X El Capitan (10.11)

Older versions may work but aren't regularly tested. Bug reports for older
versions are welcome.

Install
-------

Read, then run the script:

`bash <(curl -s https://raw.githubusercontent.com/blackjackcf/grindr-laptop/master/mac) 2>&1 tee ~/laptop.log`

Or, if you want to run it locally, pull down this repo and:

`sh mac 2>&1 | tee ~/laptop.log`  

Debugging
---------

Your last Laptop run will be saved to `~/laptop.log`.

What it sets up
---------------

Mac OS X tools:

* [Homebrew] for managing operating system libraries.

[Homebrew]: http://brew.sh/

Unix tools:

* [Exuberant Ctags] for indexing files for vim tab completion
* [Git] for version control
* [OpenSSL] for Transport Layer Security (TLS)
* [RCM] for managing company and personal dotfiles
* [The Silver Searcher] for finding things in files
* [Tmux] for saving project state and switching between projects
* [Zsh] as your shell

[Exuberant Ctags]: http://ctags.sourceforge.net/
[Git]: https://git-scm.com/
[OpenSSL]: https://www.openssl.org/
[RCM]: https://github.com/thoughtbot/rcm
[The Silver Searcher]: https://github.com/ggreer/the_silver_searcher
[Tmux]: http://tmux.github.io/
[Zsh]: http://www.zsh.org/

Image tools:

* [ImageMagick] for cropping and resizing images

Testing tools:

* [Qt] for headless JavaScript testing via Capybara Webkit

[Qt]: http://qt-project.org/

Programming languages and configuration:

* [Bundler] for managing Ruby libraries
* [Node.js] and [NPM], for running apps and installing JavaScript packages
* [Rbenv] for managing versions of Ruby
* [Ruby Build] for installing Rubies
* [Ruby] stable for writing general-purpose code

[Bundler]: http://bundler.io/
[ImageMagick]: http://www.imagemagick.org/
[Node.js]: http://nodejs.org/
[NPM]: https://www.npmjs.org/
[Rbenv]: https://github.com/sstephenson/rbenv
[Ruby Build]: https://github.com/sstephenson/ruby-build
[Ruby]: https://www.ruby-lang.org/en/

Databases:

* [MySQL] for your database needs
* [MongoDB] - The "M" in the MEAN Stack
* [Redis] for storing key-value data

[MySQL]: https://www.mysql.com/
[MongoDB]: https://www.mongodb.org/
[Redis]: http://redis.io/

It should take less than 15 minutes to install (depends on your machine).

Grindr Custom Stuff:
* [Zookeeper] for maintaining configuration
* [Maven] as your build manager for Java projects
* [DynamoDB] for all your Amazon NoSQL needs
* [Elasticsearch] for providing insight behind your data
* [RabbitMQ] for your message broker
* [IntelliJ] for your Java development needs
* [iTerm2] as a better Terminal

[Zookeeper]: https://zookeeper.apache.org/
[Maven]: https://maven.apache.org/
[DynamoDB]: https://aws.amazon.com/dynamodb/
[Elasticsearch]: https://www.elastic.co/
[RabbitMQ]: https://www.rabbitmq.com/
[IntelliJ]: https://www.jetbrains.com/idea/
[iTerm2]: https://www.iterm2.com/

Customize in `~/.laptop.local`
------------------------------

Your `~/.laptop.local` is run at the end of the Laptop script.
Put your customizations there.
For example:

```sh
#!/bin/sh

brew_install_or_upgrade 'go'
brew_install_or_upgrade 'ngrok'
brew_install_or_upgrade 'watch'

fancy_echo "Cleaning up old Homebrew formulae ..."
brew cleanup
brew cask cleanup

if [ -r "$HOME/.rcrc" ]; then
  fancy_echo "Updating dotfiles ..."
  rcup
fi
```

Write your customizations such that they can be run safely more than once.
See the `mac` script for examples.

Laptop functions such as `fancy_echo`,
`brew_install_or_upgrade`,
`brew_tap`,
`brew_launchctl_restart`, and
`gem_install_or_update`
can be used in your `~/.laptop.local`.

See the [wiki](https://github.com/thoughtbot/laptop/wiki)
for more customization examples.

Contributing
------------

Edit the `mac` file.
Document in the `README.md` file.
Follow shell style guidelines by using [ShellCheck] and [Syntastic].

```sh
brew install shellcheck
```

[ShellCheck]: http://www.shellcheck.net/about.html
[Syntastic]: https://github.com/scrooloose/syntastic

Thank you, [contributors]!

[contributors]: https://github.com/thoughtbot/laptop/graphs/contributors

By participating in this project,
you agree to abide by the thoughtbot [code of conduct].

[code of conduct]: https://thoughtbot.com/open-source-code-of-conduct

License
-------

Laptop is © 2011-2016 thoughtbot, inc.
It is free software,
and may be redistributed under the terms specified in the [LICENSE] file.

[LICENSE]: LICENSE

About thoughtbot
----------------

![thoughtbot](https://thoughtbot.com/logo.png)

Laptop is maintained and funded by thoughtbot, inc.
The names and logos for thoughtbot are trademarks of thoughtbot, inc.

We are passionate about open source software.
See [our other projects][community].
We are [available for hire][hire].

[community]: https://thoughtbot.com/community?utm_source=github
[hire]: https://thoughtbot.com?utm_source=github
