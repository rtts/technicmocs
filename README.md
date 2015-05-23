TechnicMOCs
===========

TechnicMOCs is a social news website about Lego® Technic creations,
using the [Lamernews](https://github.com/antirez/lamernews) app. You
can visit the website at
[technicmocs.created.today](http://technicmocs.created.today/). This
repository contains the code used for deploying, maintaining, testing and
providing this app.

Installation
------------

So you want to run a copy of TechnicMOCs on your own server? Great!
Here's how to do it:

### Step 1

Install the [Python Fabric](http://www.fabfile.org/) library. Fabric
is used by the deploy script to execute commands on remote
machines. To install Fabric, issue the following command on your local
machine:

    sudo pip install fabric

### Step 2

Get SSH access to a sudo user on a Debian or Ubuntu server. Firing
up a VPS and running these commands as root should do the trick:

    adduser masterbuilder
    apt-get install sudo
    adduser masterbuilder sudo

### Step 3

Open the file `deploy` in your editor and make sure the variables
`env.user`, and `env.host_string` contain the correct username and
hostname of your server. Now you can run the deploy script with the
following command:

    ./deploy

The deploy script will now automatically download, build, and install
Lamernews, Redis, nginx, uwsgi, and various dependencies. It will take
a while, so sit back and enjoy the output on your terminal screen. If
there is any error the deployment will stop immediately and the error
message is printed to your screen. Please
[open up an issue](https://github.com/rtts/technicmocs/issues) to
report any error messages!
