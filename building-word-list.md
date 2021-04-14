### Building word list
Building word list is absolutely essential if you wish to do red teaming activities like password spraying or participation in CTFs.

There are 4 main techniques that are generally used to generate word lists.
* Using regular expressions
* Extraction of words from website
* Generation of words based on human heuristics or human profiling
* Word list from keyboard random key walks

#### Word list using regular expression
Most humans have a tendency to set password(s) based on some patterns. In many organization(s), these patterns are fixed. We can make use of regular expressions to generate word list that potentially matches the existing patterns and find out passwords.
We can use python module ```Exrex```(https://pypi.org/project/exrex/) - a command line tool that generates all — or random — matching strings to a given regular expression and more. 

How to install and its usage
```
$ pip install exrex
$ exrex --help
```

#### Word list from extraction of word(s) from website
CeWL (https://github.com/digininja/CeWL/) is a ruby app which spiders a given url to a specified depth, optionally following external links, and returns a list of words which can then be used for password crackers such as John the Ripper.

CeWL also has an associated command line app, FAB (Files Already Bagged) which uses the same meta data extraction techniques to create author/creator lists.

How to install and its usage
```
$ apt install cewl
$ cewl --help
$ cewl -d 2 -m 5 -w docswords.txt https://example.com
```
### Word list from human profiling
In many past security incidences, it has been found that employees are the weak link and can be easy target for setting an initial foothold for getting into the organization. People tend to set weak passwords that matches their personal interest and personal information. There is a tool ```CUPP``` (https://github.com/Mebus/cupp) that generates potential passwords based on personal information.

How to install and its usage
```
$ git clone https://github.com/Mebus/cupp.git
$ cd cupp
$ python3 cupp.py -h
$ python3 cupp.py -i
```
### Word list from keyboard random key walks
Keyboard random walk refers to a word-list which are made up of adjacent keys on the keyboard like 12345678, or 1qazxsw2. Of course, there are many ways, key random walks can be generated. There is a python module ```kwprocessor``` (https://github.com/hashcat/kwprocessor) for tracking such key walks.


How to install and its usage
```
$ git clone https://github.com/hashcat/kwprocessor.git
$ cd kwprocessor
$ make
```
Keymaps folder contains keyboard layout for multiple languages and the routes folder has 7 pre-configured keymap walks that can be used to generate a word-list.

Usage
```
$ /kwp basechars/full.base keymaps/en.keymap routes/2-to-10-max-3-direction-changes.route
```
This causes kwp to create multiple keymap walk combinations, of 2–10 characters with a maximum of 3 direction changes.

In addition, there are popular tools like crunch ,a wordlist generator,(https://sourceforge.net/projects/crunch-wordlist/files/crunch-wordlist/crunch-3.6.tgz/downloadoad) where you can specify a standard character set or a character set you specify. crunch generates wordlists in both combination and permutation ways.

Ref:
* https://medium.com/owasp-chennai/building-word-lists-for-red-teamers-a8ba2d79ee3
