# MemCachier Daemon Deployment Tool

This is a simple tool that uses the great powers of [daemon
tools](http://cr.yp.to/daemontools.html) to give a simple way to
manage a long-lived process on a remote server.

Think of it like a cheap and cheerful Heroku interface to your server
for running and deploying simple applications. It requries that you
are using git to manage your application.

It also relies on the `start-stop-daemon` command for launching the daemon
tools `svscan` process.

## Installation
    
    $ cp dp /usr/local/bin/dp

## Usage

Simply type `dp` to get started and get some help.

To turn a application into a DP app (say a Ruby-On-Rails app or
Haskell Simple web app), simply type:

        dp init

After that, edit the following files:
  * .dp/default/config -- set the remote host you will deploy to.
  * .dp/compile -- a simple shell script specifying how to compile
    your application to a runnable process. Executed on the remote
    server.

You'll also need to edit `Procfile`, to set the name and way to launch your
app. For example:

        web: node app.js

Once done, you should be able to type:

        dp init-server

To setup the remote server to be ready for your app. After that type:

        dp deploy

To deploy the current version of your app to the server. You should
also setup the environment for the app on the remote server using:

        dp config:set

From there, you are rocking!

### Commands

DP supports the following commands:

        init            Turn current directory into a DP app.
        init-server     Start a new DP install on the remote server.
        envs            Display the configured dp deployment environments.
        config          Display app environment.
        config:get      Display a specific app env variable.
        config:set      Set a specific app env variable.
        config:setbulk  Set many app env variables.
        config:unset    Remove a specific app env variable.
        deploy          Deploy the latest version of the managed app.
        start           Start the app on the remote server.
        stop            Stop the app on the remote server.
        restart         Restart the app on the remote server.
        status          Display running state of the app on the remote server.
        auto:on         Allow app to be started automatically.
        auto:off        Disable automatic starting of app.
        version         Display version of app deployed on remote server.
        logs            Display latest log output of app.
        run             Run a command on the remote server.

### Git Required

DP relies on you using git to manage all the required files for your
application. This is since DP uses git to determine the files that are
part of your application and package them up to transfer to the remote
application server.

DP supports using git submodules, however, it does not support the
`export-ignore` git-attribute to exclude files from deployment. All
files that are in your git repo will be transfered to the application
server.

## Licensing

This library is under the GPLv2

## Get involved!

We are happy to receive bug reports, fixes, documentation enhancements,
and other improvements.

Please report bugs via the
[github issue tracker](http://github.com/memcachier/dp/issues).

Master [git repository](http://github.com/memcachier/dp):

* `git clone git://github.com/memcachier/dp.git`

## Authors

This library is written and  maintained by MemCachier,
<info@memcachier.com>.

