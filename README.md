# cliaoke

[![Travis CI](https://img.shields.io/travis/jessfraz/cliaoke.svg?style=for-the-badge)](https://travis-ci.org/jessfraz/cliaoke)
[![GoDoc](https://img.shields.io/badge/godoc-reference-5272B4.svg?style=for-the-badge)](https://godoc.org/github.com/jessfraz/cliaoke)

Command Line Karaoke

 * [Installation](README.md#installation)
   * [Binaries](README.md#binaries)
   * [Via Go](README.md#via-go)
   * [Requirements](README.md#requirements)
      * [Linux](README.md#linux)
         * [Via Docker](README.md#via-docker)
      * [OSX](README.md#osx)
 * [Usage](README.md#usage)
   * [List all songs](README.md#list-all-songs)
   * [Play a song](README.md#play-a-song)

## Installation

### Binaries

For installation instructions from binaries please visit the [Releases Page](https://github.com/jessfraz/cliaoke/releases).

### Via Go

```console
$ go get github.com/jessfraz/cliaoke
```

### Requirements

#### Linux

- Download `fluidsynth` and soundfonts on debian this was `fluid-soundfont-gm`.

##### Via Docker

```
$ docker run --rm -it \
    --device /dev/snd \
    jess/cliaoke hard_knock_life
DJ cliaoke on the request line.
Bringing up the track Hard Knock Life...
```


#### OSX

This assumes you have setup `fluidsynth` in the following way:

(grab a copy of `GeneralUser_GS_1.44-FluidSynth.zip` from one of the mirrors in  http://www.filewatcher.com/m/GeneralUser_GS_1.44-FluidSynth.zip.28596599-0.html)

```console
$ brew install fluidsynth
$ unzip GeneralUser_GS_1.44-FluidSynth.zip
$ mkdir -p /usr/local/share/fluidsynth
$ mv GeneralUser\ GS\ 1.44\ FluidSynth/GeneralUser\ GS\ FluidSynth\ v1.44.sf2 /usr/local/share/fluidsynth/generaluser.v.1.44.sf2
```

Running `cliaoke` with no arguments will list all the available songs. Once downloaded the songs are saved in a `~/.cliaoke/` directory.

**Caveats for Mac Users**

- You *must* install `fluidsynth` according to the instructions below.
- Sometimes the search for lyrics selects the wrong one, *whomp whomp*.
- The lines being printed are not synced with the song. (maybe there is a way to parse the lyric metadata from a .mid file?)


## Usage

```console
$ cliaoke -h
cliaoke -  Command line karaoke.

Usage: cliaoke <command>

Flags:

  -d  enable debug logging (default: false)

Commands:

  version  Show the version information.
```

### List all songs

**NOTE:** This does not mean you have all these files locally, when you choose
a song (if you have no already downloaded it from this repo) it will be
downloaded for you.

```console
$ cliaoke
COMMAND                             TITLE                               ARTIST
1979                                1979                                Smashing Pumpkins
99_ways_to_die                      99 Ways To Die                      Megadeth
...
hard_knock_life                     Hard Knock Life                     Jay-Z
...
missing_you                         Missing You                         Puff Daddy
mo_money_mo_problems                Mo Money Mo Problems                Notorious BIG
...
```

### Play a song

```console
$ cliaoke mo_money_mo_problems
DJ cliaoke on the request line.
Bringing up the track Mo Money Mo Problems...
```


[![Analytics](https://ga-beacon.appspot.com/UA-29404280-16/cliaoke/README.md)](https://github.com/jessfraz/cliaoke)
