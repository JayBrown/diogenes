# Diogenes

Diogenes is a tool for searching, browsing and reading the databases
of ancient texts, primarily in Latin and Greek, that are published by
the Thesaurus Linguae Graecae and the Packard Humanities Institute.


## Installation
### Download

Maybe one day I'll prepare a script to install all the app. In the 
meanwhile, you could either clone this repository

> `git clone https://github.com/Doc73/diogenes.git`

or download a zip file containing all the repo from GitHub or by terminal:

> `wget https://github.com/Doc73/diogenes/archive/master.zip`

Unzip this file with your preferred file and archive manager 
or via terminal:

> `unzip master.zip`

Now, we will find a folder called `diogenes-master`.


### Building [optional]

There are a few files that need to be built before Diogenes can be
run.

In Debian and Debian-based distros (and maybe in other distributions), 
you should install some required packages:

> `sudo apt install librsvg2-bin build-essential`

Then, run these commands:

> `cd /path/to/diogenes-master`

> `make`

If the terminal returns no errors, don't worry and go to next step 
without closing terminal.


### Installation

In this sample we will install Diogenes in `/opt/`: change the path 
according your preferences. Run these commands:

> `cd ..`

> `sudo mv diogenes-master /opt/`

Then 

> `mkdir -p ~/bin/`

> `cp /opt/diogenes/linux/diogenes-server ~/home/bin`

> `cp /opt/diogenes/linux/diogenes-server.desktop ~/.local/share/applications/`

Logout and login.


## Running the server

The Diogenes server can be started using the script:

> `diogenes-browser/perl/diogenes-server.pl`

For full usage details run it like this:

> `diogenes-browser/perl/diogenes-server.pl -?`


## Building the morphology data & dictionaries

Diogenes uses several dictionaries, as well as pre-computed
morphology tables, which need to be built before use. You can build
them yourself, or download prebuilt copies from:

> [https://gitlab.com/diogenes/diogenes-prebuilt/tree/master](https://gitlab.com/diogenes/diogenes-prebuilt/tree/master)

Be aware that a lot of memory is required to build the morphology
tables (around 25GiB).

There are two options in building the morphology data, either using
wordlists from Perseus' free corpus, or using the TLG and PHI
wordlists. The latter has the advantage of greater coverage when
reading TLG and PHI texts, while the former has the advantage of
being freely available.

To build morphology and dictionaries using the Perseus corpus:

>  `make -f mk.perseusdata`

To build morphology and dictionaries using the TLG and PHI corpus:

>  `make -f mk.tlgdata PHIDIR=/path/to/phi TLGDIR=/path/to/tlg_e`

The morphology data and dictionary files will be built in the
`dependencies/data/` directory, which will automatically be read
by `diogenes-server.pl`.


## Credits

Forked from [nickjwhite](https://github.com/nickjwhite/diogenes).

Many thanks also to

- [P. J. Heslin](http://community.dur.ac.uk/p.j.heslin/Software/Diogenes/)

