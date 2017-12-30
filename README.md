# masc

<img align="left" height="200px" width="200px" src="https://www.arkabytes.com/img/masc.jpg">

A malware (web) scanner developed during [CyperCamp](http://www.cybercamp.es) Hackathon 2017

## About

[homepage](https://sfaci.github.io/masc)

[PyPI](https://pypi.python.org/pypi/masc)

## Features

At the moment, there are some features avaiable for any type of website (custom or CMS)  and some of them only available for specific
platforms:

* Scan any website for malware using OWASP WebMalwareScanner checksum, YARA rules databases and ClamAV engine (if available)
* Perform some cleaning operations to improve website protection
* Monitor the website for changes. Details are written in a log file
* Scan your site to know if it has been infected with some malware
* List your local backups
* Logging support
* Backup your site
* Restore website
* Scan for suspect files and compare with a clean installation (for Wordpress and Drupal)
* Clean up your site to avoid giving extra information to attackers (only available for Wordpress)

## Requirements

First of all, notice that this tool is developed under Linux and, at the moment, it has been tested only under this Operating System

* Python >= 3
* Some Python libraries
  * python-magic
  * yara-python
  * watchdog
  * termcolor
  * pypandoc
  * progress
```bash
santi@zenbook:$ pip3 install python-magic yara-python watchdog termcolor pypandoc progress
```
* ClamAV to integrate with its engine (optional but recommended)

#### Notice

_masc_ is developed under Linux and it has not been tested under any other Operating System.

Anyway, it should run without problems under any Unix-friendly OS. In particular, in Mac OSX I have noticed it's neccesary to install
[Homebrew](https://brew.sh) to use python-magic library propery as _libmagic_. Check first the previous link to the _brew_ homepage and then
you will be able to install as I show below:

```bash
santi@zenbook:$ brew install libmagic
```

## Installation

To install _masc_ on your computer, you can download a [release](https://github.com/sfaci/masc/releases), untar it and try.
You can also install it usign pip ('pip3 install masc')

## Usage

```bash

masc 0.2.2 (http://github.com/sfaci/masc)
usage: masc.py [-h] [--add-file FILENAME] [--add-word STRING] [--clean-cache]
               [--clean-site] [--list-backups] [--make-backup] [--monitor]
               [--name NAME] [--path PATH] [--rollback] [--scan]
               [--site-type {wordpress,drupal,custom}]

optional arguments:
  -h, --help            show this help message and exit
  --add-file FILENAME   Add a suspect file to the dictionary
  --add-word STRING     Add a suspect content to the dictionary
  --clean-cache         Clean masc cache (cache and logs files, NO backups)
  --clean-site          Clean up the site to hide information to attackers
  --list-backups        List local backups
  --make-backup         Create a local backup of the current installation
  --monitor             Monitor site to detect changes
  --name NAME           Name assigned to the scanned installation
  --path PATH           Website installation path
  --rollback            Restore a local backup
  --scan                Scan website for malware
  --site-type {wordpress,drupal,custom}
                        which type of web you want to scan:: wordpress,
                        joomla, drupal or magento
```

## Test

There is a repository in the Docker Hub to perform tests [masc-wordpress](https://hub.docker.com/r/sfaci/masc-wordpress/)

## Documentation

You can find a complete tutorial about how to use _masc_ in the [wiki](https://github.com/sfaci/masc/wiki)

## Thanks

Thanks to [OWASP WebMalwareScanner](https://github.com/maxlabelle/WebMalwareScanner) for some ideas and the signatures databases with checksums and YARA
rules (and how to load it to work with). 

## Author

Santiago Faci <santi@arkabytes.com>
