# 200302 发现首页问题

无法正常解析最新文章

![](http://ipic.7.zoomquiet.top/zq/2020-03-02-ScreenShot%202020-03-02%2017.52.36.jpg)

## 本地调试 Jekyll

Command Line Usage

The Jekyll gem makes a jekyll executable available to you in your terminal.

You can use this command in a number of ways:

    jekyll new PATH - Creates a new Jekyll site with default gem-based theme at specified path. The directories will be created as necessary.

    jekyll new PATH --blank - Creates a new blank Jekyll site scaffold at specified path.

    jekyll build or jekyll b - Performs a one off build your site to ./_site (by default)

    jekyll serve or jekyll s - Builds your site any time a source file changes and serves it locally

    jekyll doctor - Outputs any deprecation or configuration issues

    jekyll clean - Removes all generated files: destination folder, metadata file, Sass and Jekyll caches.

    jekyll help - Shows help, optionally for a given subcommand, e.g. jekyll help build

    jekyll new-theme - Creates a new Jekyll theme scaffold

Typically you’ll use jekyll serve while developing locally and jekyll build when you need to generate the site for production.

To change Jekyll’s default build behavior have a look through the configuration options.

### install

> # Install Homebrew

/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

> # Install rbenv and ruby-build

brew install rbenv

> # Set up rbenv integration with your shell

rbenv init

> # Check your installation

curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash


༄  brew install rbenv

    Updating Homebrew...
    ==> Auto-updated Homebrew!
    Updated 3 taps (caskroom/fonts, dart-lang/dart and heroku/brew).
    ==> Updated Formulae
    heroku/brew/heroku ✔                                                  dart-lang/dart/dart

    ==> Installing dependencies for rbenv: ruby-build
    ==> Installing rbenv dependency: ruby-build
    ==> Downloading https://github.com/rbenv/ruby-build/archive/v20191004.tar.gz
    ==> Downloading from https://codeload.github.com/rbenv/ruby-build/tar.gz/v20191004
    ######################################################################## 100.0%
    ==> ./install.sh
    🍺  /usr/local/Cellar/ruby-build/20191004: 459 files, 230.7KB, built in 15 seconds
    ==> Installing rbenv
    ==> Downloading https://mirrors.ustc.edu.cn/homebrew-bottles/bottles/rbenv-1.1.2.sierra.bottle.tar.gz
    ######################################################################## 100.0%
    ==> Pouring rbenv-1.1.2.sierra.bottle.tar.gz
    🍺  /usr/local/Cellar/rbenv/1.1.2: 36 files, 65.2KB
    ==> `brew cleanup` has not been run in 30 days, running now...
    Removing: /usr/local/Cellar/libpng/1.6.36... (27 files, 1.2MB)
    Removing: /usr/local/Cellar/wxmac/3.0.4_1... (813 files, 23.8MB)
    ...



༄  curl -fsSL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-doctor | bash

    Checking for `rbenv' in PATH: /usr/local/bin/rbenv
    Checking for rbenv shims in PATH: OK
    Checking `rbenv install' support: /usr/local/bin/rbenv-install (ruby-build 20191004)
    Counting installed Ruby versions: none
      There aren't any Ruby versions installed under `/Users/zoomq/.rbenv/versions'.
      You can install Ruby versions like so: rbenv install 2.2.4
    Checking RubyGems settings: OK
    Auditing installed plugins: OK


༼DU363༽⎇ master U:1 ✗༽/opt/data/Sites/101.camp/FM/fm༽

༄  rbenv install 2.6.5

    ruby-build: using openssl from homebrew
    Downloading ruby-2.6.5.tar.bz2...
    -> https://cache.ruby-lang.org/pub/ruby/2.6/ruby-2.6.5.tar.bz2



    Installing ruby-2.6.5...
    ruby-build: using readline from homebrew
    Installed ruby-2.6.5 to /Users/zoomq/.rbenv/versions/2.6.5

༄   rbenv global 2.6.5

༄  source ~/.bash_profile

༄  ruby -v

    ruby 2.6.5p114 (2019-10-01 revision 67812) [x86_64-darwin16]


༄  gem install --user-install bundler jekyll

    Fetching bundler-2.1.4.gem
    WARNING:  You don't have /Users/zoomq/.gem/ruby/2.6.0/bin in your PATH,
          gem executables will not run.
    Successfully installed bundler-2.1.4
    Parsing documentation for bundler-2.1.4
    Installing ri documentation for bundler-2.1.4
    Done installing documentation for bundler after 3 seconds
    Fetching colorator-1.1.0.gem
    ...

    Parsing documentation for jekyll-4.0.0
    Installing ri documentation for jekyll-4.0.0
    Done installing documentation for public_suffix, addressable, colorator, http_parser.rb, eventmachine, em-websocket, concurrent-ruby, i18n, ffi, sassc, jekyll-sass-converter, rb-fsevent, rb-inotify, listen, jekyll-watch, kramdown, kramdown-parser-gfm, liquid, mercenary, forwardable-extended, pathutil, rouge, safe_yaml, unicode-display_width, terminal-table, jekyll after 81 seconds
    27 gems installed


> ༄  gem env


    RubyGems Environment:
      - RUBYGEMS VERSION: 3.0.3
      - RUBY VERSION: 2.6.5 (2019-10-01 patchlevel 114) [x86_64-darwin16]
      - INSTALLATION DIRECTORY: /Users/zoomq/.rbenv/versions/2.6.5/lib/ruby/gems/2.6.0
      - USER INSTALLATION DIRECTORY: /Users/zoomq/.gem/ruby/2.6.0
      - RUBY EXECUTABLE: /Users/zoomq/.rbenv/versions/2.6.5/bin/ruby
      - GIT EXECUTABLE: /usr/bin/git
      - EXECUTABLE DIRECTORY: /Users/zoomq/.rbenv/versions/2.6.5/bin
      - SPEC CACHE DIRECTORY: /Users/zoomq/.gem/specs
      - SYSTEM CONFIGURATION DIRECTORY: /Users/zoomq/.rbenv/versions/2.6.5/etc
      - RUBYGEMS PLATFORMS:
        - ruby
        - x86_64-darwin-16
      - GEM PATHS:
         - /Users/zoomq/.rbenv/versions/2.6.5/lib/ruby/gems/2.6.0
         - /Users/zoomq/.gem/ruby/2.6.0
      - GEM CONFIGURATION:
         - :update_sources => true
         - :verbose => true
         - :backtrace => false
         - :bulk_threshold => 1000
      - REMOTE SOURCES:
         - https://rubygems.org/
      - SHELL PATH:
         - /Users/zoomq/.rbenv/versions/2.6.5/bin
         - /usr/local/Cellar/rbenv/1.1.2/libexec
         - /Users/zoomq/miniconda3/condabin
         - /Users/zoomq/.pyenv/plugins/pyenv-virtualenv/shims
         - /Users/zoomq/.pyenv/shims
         - ~/.pyenv/bin
         - /usr/local/opt/openssl@1.1/bin
         - /Users/zoomq/.pyenv/plugins/pyenv-virtualenv/shims
         - /Users/zoomq/.pyenv/shims
         - /Users/zoomq/.pyenv/bin
         - /opt/bin
         - /usr/local/sbin
         - /usr/local/bin
         - /usr/local/opt/libxml2/bin
         - ~/Works/flutter.dart/flutter/bin
         - /Users/zoomq/.gem/ruby/2.6.0/bin
         - /Users/zoomq/.rbenv/shims
         - /usr/local/opt/ruby/bin
         - /usr/local/opt/coreutils/libexec/gnubin
         - /usr/local/opt/coreutils/libexec/gnubin
         - /usr/bin
         - /bin
         - /usr/sbin
         - /sbin
         - /usr/local/bin
         - /usr/local/Cellar/go/1.12.5/libexec/bin
         - /Users/zoomq/Works/google/golang/proj/bin



## refer.

- [Installation | Jekyll • Simple, blog-aware, static sites](https://jekyllrb.com/docs/installation/)
    + [Jekyll on macOS | Jekyll • Simple, blog-aware, static sites](https://jekyllrb.com/docs/installation/macos/)


## changrlog

- 200302 init.