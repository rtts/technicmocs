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

### Step 1

Get access to a Debian-based server that uses
[systemd](http://freedesktop.org/wiki/Software/systemd/), such as
Debian 8 or Ubuntu 15.04. Make sure your user has sudo privileges.
On a fresh [Linode](https://www.linode.com/) or [DigitalOcean]
(https://www.digitalocean.com/) VPS, running these commands as root
will do the trick:

    adduser masterbuilder
    adduser masterbuilder sudo

### Step 2

Install the [Python Fabric](http://www.fabfile.org/) library on your
local machine by running this command as root:

    pip install fabric

(Note: If this fails with a "command not found" error, please install
[Python](https://www.python.org/) and [pip](https://pip.pypa.io/) with
your operating system's package manager)

### Step 3

Open the file `deploy` in your editor and make sure the variables
`env.user`, and `env.host_string` contain the correct username and
hostname of the remote machine. Now run the deploy script with the
following command:

    ./deploy

The deploy script will automatically download, build, and install
[Lamernews](https://github.com/antirez/lamernews),
[Redis](https://github.com/antirez/redis),
[nginx](http://wiki.nginx.org/),
[uwsgi](https://uwsgi-docs.readthedocs.org/), and various
dependencies. You will be asked for the remote machine's sudo password
once or twice.  Sit back, relax, and enjoy the output on your terminal
screen!

Please [open up an issue](https://github.com/rtts/technicmocs/issues)
to report any error messages.

Note: you can safely run the deploy multiple times. Subsequent runs
will only update the configuration files, without re-installing all
the dependencies.
