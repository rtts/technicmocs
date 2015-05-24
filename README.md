TechnicMOCs
===========

TechnicMOCs is a social news website about Lego® Technic creations,
using the [Lamernews](https://github.com/antirez/lamernews) app. You
can visit the website at
[technicmocs.created.today](http://technicmocs.created.today/). This
repository contains the code used for deploying, maintaining, testing and
providing this app.

Requirements
------------

A Debian-based Linux server that uses
[systemd](http://freedesktop.org/wiki/Software/systemd/). Debian 8 and
Ubuntu 15.04 have both successfully been tested.

Installation
------------

### Step 1

Install the [Python Fabric](http://www.fabfile.org/) library on your
local machine:

    pip install fabric

### Step 2

Set up a sudo user on the remote machine. Running these commands as
root should do the trick:

    adduser masterbuilder
    adduser masterbuilder sudo

### Step 3

Open the file `deploy` in your editor and make sure the variables
`env.user`, and `env.host_string` contain the correct username and
hostname of the remote machine. Now run the deploy script with the
following command:

    ./deploy | tee installation.log

The deploy script will automatically download, build, and install
Lamernews, Redis, nginx, uwsgi, and various dependencies. It will take
a while, so sit back and enjoy the output on your terminal screen. If
there is any error, the deployment will stop immediately and the error
message is printed to your screen and to the installation log. Please
[open up an issue](https://github.com/rtts/technicmocs/issues) to
report any error messages!
