# deckshare.net

[![Build Status](http://img.shields.io/travis/thetallgrassnet/deckshare.svg?style=flat)](https://travis-ci.org/thetallgrassnet/deckshare)
[![Dependency Status](http://img.shields.io/gemnasium/thetallgrassnet/deckshare.svg?style=flat)](https://gemnasium.com/thetallgrassnet/deckshare)
[![Code Climate](http://img.shields.io/codeclimate/github/thetallgrassnet/deckshare.svg?style=flat)](https://codeclimate.com/github/thetallgrassnet/deckshare)
[![Test Coverage](http://img.shields.io/codeclimate/coverage/github/thetallgrassnet/deckshare.svg?style=flat)](https://codeclimate.com/github/thetallgrassnet/deckshare)
[![Huboard](https://img.shields.io/github/issues/thetallgrassnet/deckshare.svg?style=flat)](https://huboard.com/thetallgrassnet/deckshare/)
[![Gitter](https://img.shields.io/badge/gitter-join%20chat-brightgreen.svg?style=flat)](https://gitter.im/thetallgrassnet/deckshare?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

Manage and share your TCG collections and decklists.

## Development

### Requirements

 * Ruby 2.1.5 (preferably installed by [RVM](http://rvm.io/))
 * JDK 1.7

### Setup

 1. Clone the project and `cd` into it:

        $ git clone https://github.com/thetallgrassnet/deckshare.git
        $ cd deckshare

 2. Bootstrap the application:

        $ bin/setup

    What this does (you don't need to run these commands): install dependencies,

        $ gem install bundler
        $ bundle install

    and set up and start the development and test databases:

        $ bundle exec rake neo4j:setup_all

    then clean up logs and temp files and restart the application server if it's
    running.

 3. Start the server:

        $ bin/rails s

#### Updating

    $ git pull
    $ bin/setup

### Testing

    $ bin/rspec
