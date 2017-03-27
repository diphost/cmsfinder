CMS Finder
==========

Detect Web CMS software type and version in specified path. CMS signatures and actual versions database.

Initially based on weakly maintained https://github.com/JamesDooley/VersionFinder

Features
--------
* Fast and simple
* Only Python 2 in the requirements
* Russian 1C-Bitrix, UMI.CMS and NetCat commercial CMS detection
* It is possible to define outdated versions in different CMS branches
* Single scan from argument and bulk scan paths from file available

What for
--------

It is designed to search for potentially vulnerable CMS. This helps sell customers a complementary service

Usage
-----

### Command help

```sh
./cmsfinder --help
usage: cmsfinder [-h] [-v] [-s FILENAME] [-l [FILENAME] | PATH]

positional arguments:
  PATH           Path to site
  
  optional arguments:
    -h, --help     show this help message and exit
    -v             increase verbosity of the logging, -vvv for debug
    -s FILENAME    Signatures file
    -l [FILENAME]  Site paths from file
```

### Scan single path (DocumentRoot)

```sh
./cmsfinder -v /var/www/www-root/htdocs
```

### Scan paths from file

```sh
./cmsfinder -v -l sitelist.lst >result.lst
```

### Result string

> PATH CMS VERSION LAST SUPPORT

* PATH - path of site, i.e. DocumentRoot
* CMS - friendly name of cms signature
* VERSION - detected CMS version
* LAST - newest version on detected branch with one of the prefix:
  * '<' - detected version is older than latest version on this branch
  * '=' - detected version is the freshest version on this branch
  * '>' - detected version is newer than latest version on this branch (oh!)
* SUPPORT - support level
  * 'eol' - End Of Life - this branch not supported yet
  * 'limited' - may or may not get updates
  * 'supported' - fully supported
  * 'current' - the freshest supported branch

```
~$ ./cmsfinder /var/www/www-root/htdocs
/var/www/www-root/htdocs wordpress 4.6.2 <4.6.4 limited
~$ 
```

TODO
----

* Anime chan mascot
* Developers Guide
* Implement github or gitlab flow
* Make custom signature sets
* Cover the code with comments
* Fill in supported versions for all CMS. Only Drupal, WordPress and Joomla presents
* Add more popular CMSes
* Ansible role (good idea for outsourcing automation :)
* Improve some check algorithms

---
[![UNLICENSE](noc.png)](UNLICENSE)

