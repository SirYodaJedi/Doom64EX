Doom64EX [![Build Status](https://travis-ci.org/svkaiser/Doom64EX.svg?branch=master)](https://travis-ci.org/svkaiser/Doom64EX) [![Build status](https://ci.appveyor.com/api/projects/status/04kswu014uwrljrd/branch/master?svg=true)](https://ci.appveyor.com/project/dotfloat/doom64ex/branch/master)
========

Doom64EX is a reverse-engineering project aimed to recreate Doom64 as close as possible with additional modding features.

**NOTE for Linux users:** As of Feb. 24, 2016, the save data is located in `$XDG_DATA_HOME/doom64ex` (typically `~/.local/share/doom64ex`) and not in `~/.doom64ex`. The files can be safely moved to their new home.

## Dependencies

* SDL2
* SDL2_net
* zlib
* libpng
* FluidSynth

## Compiling

### Linux

Clone this repo

    $ git clone https://github.com/svkaiser/Doom64EX

Create a new directory inside the repo root where compilation will take place

    $ mkdir Doom64EX/temp
    $ cd Doom64EX/temp

Run cmake and make

    $ cmake .. && make

Install doom64ex (on macOS do not do this as root or with `sudo`)

    # make install

## Usage

Doom64EX needs the Doom 64 data to be present in any of the following directories:

* The directory in which `doom64ex` resides
* `$XDG_DATA_HOME/doom64ex` (eg. `~/.local/share/doom64ex`)
* `/usr/local/share/games/doom64ex`
* `/usr/local/share/doom64ex`
* `/usr/share/games/doom64ex`
* `/usr/share/doom64ex`
* `~/Library/Application Support/doom64ex` (macOS only)

The data files are:

* `kex.wad` (Generated by cmake)
* `doom64.wad`
* `doomsnd.sf2`

To generate the two latter files, acquire a Doom64 ROM and run:

    $ doom64ex -wadgen PATH_TO_ROM

This will generate the required files and place them in `$XDG_DATA_DIR/doom64ex`.

After this you can play.

    $ doom64ex
