CMS Finder
==========

Detect CMS software type and version in specified path. CMS signatures and actual versions database.

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

```./cmsfinder --help
usage: cmsfinder [-h] [-v] [-s FILENAME] [-l [FILENAME] | PATH]

positional arguments:
  PATH           Path to site
  
  optional arguments:
    -h, --help     show this help message and exit
    -v             increase verbosity of the logging, -vvv for debug
    -s FILENAME    Signatures file
    -l [FILENAME]  Site paths from file
```

TODO
----

* Cover the code with comments
* Fill in supported versions for all CMS. Only Drupal, WordPress and Joomla presents
* Add more popular CMSes
* Ansible role (good idea for outsourcing automation :)
* Improve some check algorithms

---
[![UNLICENSE](noc.png)](UNLICENSE)

