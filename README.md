# find_orb

### Orbit determination from observations

More about Find_Orb (what it does,  how to use it,  pre-built Windows
executables) at

[`https://www.projectpluto.com/find_orb.htm`](https://www.projectpluto.com/find_orb.htm)

This project includes code for building Linux,  Windows,  and BSD
(and possibly OS/X) versions of the interactive Find_Orb orbit
determination software, the non-interactive `fo` software,  and
the `fo_serve.cgi` program that underlies the
[on-line Find_Orb service](https://www.projectpluto.com/fo.htm).
(For a lot of purposes,  the on-line service or pre-built .EXEs
may be all you really need.)

Right now,  only the Linux and BSD versions can be built with
what's posted here.  (You can probably build for OS/X,  too,
but I've not heard any reports on that recently.) I've not
gotten around to documenting the Windows build process yet;  I
just provide the aforementioned pre-built EXEs.  Sadly,  the
Windows builds require the Microsoft compiler,  due to an
unfortunate early choice to use MFC.

You can [click here for directions on building Find_Orb from
the source in this repository.](https://projectpluto.com/find_sou.htm).

As is described at the above link,  this project depends on three
of my other projects :

- [`jpl_eph`](https://github.com/Bill-Gray/jpl_eph) (code to read JPL ephemerides)
- [`sat_code`](https://github.com/Bill-Gray/sat_code) (code for Earth-orbiting satellite ephemerides)
- [`lunar`](https://github.com/Bill-Gray/lunar) (basic astronomical ephemeris/time functions)

At some point,  I'll probably document the build procedure for
Windows,  but it does appear that most Windows users just want
pre-built executables.

# Installation instructions

In the following, the installation instructions on a Linux system are given.

## Preliminary steps

Two packages are required to build `find_orb`: `ncurses` and `libcurl`. On a Debian-based system, they can be installed with the following command:

    $ sudo apt install libncurses-dev
    $ sudo apt install libcurl4-openssl-dev

## Downloading the source code and the dependencies

The source code of `find_orb` and the dependencies should be saved in the same directory, named `<DOWNLOAD_DIR>`. The following commands will download the source code of `find_orb` and the dependencies:

    $ cd <DOWNLOAD_DIR>
    $ git clone <github-path-to/Bill-Gray/find_orb>
    $ git clone <github-path-to/Bill-Gray/jpl_eph>
    $ git clone <github-path-to/Bill-Gray/sat_code>
    $ git clone <github-path-to/Bill-Gray/lunar>
    $ git clone <github-path-to/Bill-Gray/miscell>

## Building find_orb and the dependencies

There is a shell script `INSTALL.sh` in the `find_orb` directory that builds `find_orb` and the dependencies. 
Executing permissions must be given to the script:

    $ cd <DOWNLOAD_DIR>/find_orb
    $ chmod +x INSTALL.sh

The script can be executed with the following command:

    $ sudo ./INSTALL.sh -d <DOWNLOAD_DIR>

The `-d` option is mandatory and specifies the directory where the dependencies are located. 
Note that `<DOWNLOAD_DIR>` is `..` (i.e., the parent directory of `find_orb`).
