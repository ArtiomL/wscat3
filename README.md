# <img align="center" src="img/wscat.svg" width="70">&nbsp;&nbsp;wscat3
[![Build Status](https://img.shields.io/travis/ArtiomL/wscat.svg)](https://travis-ci.org/ArtiomL/wscat)
[![Releases](https://img.shields.io/github/release/ArtiomL/wscat.svg)](https://github.com/ArtiomL/wscat/releases)
[![Commits](https://img.shields.io/github/commits-since/ArtiomL/wscat/v3.0.2.svg?label=commits%20since)](https://github.com/ArtiomL/wscat/commits/master)
[![Maintenance](https://img.shields.io/maintenance/yes/2018.svg)](https://github.com/ArtiomL/wscat/graphs/code-frequency)
[![Issues](https://img.shields.io/github/issues/ArtiomL/wscat.svg)](https://github.com/ArtiomL/wscat/issues)
[![npm Downloads](https://img.shields.io/npm/dt/wscat3.svg)](https://www.npmjs.com/package/wscat3)
[![License](https://img.shields.io/badge/license-BSD3-blue.svg)](/LICENSE)

&nbsp;&nbsp;

## Table of Contents
- [Description](#description)
- [Installation](#installation)
- [Help](#--help)
- [License](LICENSE)

&nbsp;&nbsp;

## Description

WebSocket Netcat with piping and subprotocol support.

Forked from [jnordberg/wscat](https://github.com/jnordberg/wscat).

&nbsp;&nbsp;

## Installation

```
npm install -g wscat3
```

&nbsp;&nbsp;

## Examples

If you ever used `nc`, `wscat` works pretty much the same.

### Connect to a server

```
$ wscat echo.websocket.org
Hello
Hello
Who's there?
Who's there?
^D

```

### Chat

Server:

```
$ wscat -l 12345
Hi there!
Hi!
It's nice to speak to someone who just dosn't repeat everything I say back at me.
Yeah! Isn't it?!
Sorry, gotta run...
^D

```

Client:

```
$ wscat localhost:12345
Hi there!
Hi!
It's nice to speak to someone who just dosn't repeat everything I say back at me.
Yeah! Isn't it?!
Sorry, gotta run...
```

### Transfer a file

Server:

```
$ wscat -b -l 12345 < ~/Desktop/mycat.jpg
```

Client:

```
$ wscat -b localhost:12345 > igotacat.jpg
```

Note that you can have the client send the file as well, after the connection has been setup `wscat` does not differentiate between server/client.


&nbsp;&nbsp;

## --help
```shell
$ wscat --help
usage: wscat [-h] [-v] [-l PORT] [-b] [-k] [-d] [-s SUBP] [address]

Positional arguments:
  address

Optional arguments:
  -h, --help            Show this help message and exit.
  -v, --version         Show program's version number and exit.
  -l PORT, --listen PORT
                        Start a websocket server on PORT.
  -b, --binary          Use binary WebSockets.
  -k, --keep-open       Do not close the socket after EOF.
  -d, --deflate         Use per-message deflate.
  -s SUBP, --subprotocol SUBP
                        WebSocket subprotocol
```
