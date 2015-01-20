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

  * Ruby (the OS X or your Linux distribution's default installation is okay)
  * [VirtualBox](https://www.virtualbox.org/)
  * [Docker](https://www.docker.com/)
  * [boot2docker](http://boot2docker.io/) on Mac OS X or Windows

This project uses Docker images and containers to ensure parity between
development, testing, and production environments, without needing to keep
multiple dependencies manually up-to-date on different machines. The correct
versions of Ruby and Neo4j are used from Docker images, and containers for the
application code and database instance are created and linked.

### Setup

 1. Clone the project and `cd` into it:

        $ git clone https://github.com/thetallgrassnet/deckshare.git
        $ cd deckshare

 2. Bootstrap the application:

        $ bin/setup

    This builds a Docker image for the application, then creates Docker
    containers for the development and test databases and the application code,
    mounting the project directory to the application directory in the
    application container, and the `db/neo4j/[environment]/data/graph.db`
    directory to the location of the `graph.db` directory in the database
    containers, and linking the containers appropriately.

 3. Start the server using the helper script at `bin/d`:

        $ bin/d start

    The helper script can be passed one of four different commands to start or
    stop the server, run specs, or run an arbitrary command. The `start` command
    starts the Neo4j database for the development environment, waits for it to
    be ready to accept connections, then starts the application server. The
    address and port for connecting to the server will be shown above the server
    output in the terminal.

#### Updating

    $ git pull
    $ bin/setup

Also re-run `bin/setup` whenever any changes are made to the `Gemfile` or
`Dockerfile` to rebuild the application image and containers.

### Testing

    $ bin/d spec [ARGUMENTS]

### Running commands

    $ bin/d run COMMAND [ARGUMENTS]

For example, to start a Rails console:

    $ bin/d run bin/rails c

### Shutdown

    $ bin/d stop
