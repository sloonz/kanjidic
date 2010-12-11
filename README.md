# Kanjidic
## Presentation

[https://github.com/sloonz/kanjidic](Kanjidic) is a really simple Kanji
Dictonary written in Ruby/GTK. It allows you to find kanjis by:

* Fuzzy skip code
* Multi-radical search
* Similar kanjis

This is achieved by the integration of three different databases :

* The famous
[http://www.csse.monash.edu.au/~jwb/kanjidic2/](kanjidic2.xml) file
* [http://www.csse.monash.edu.au/~jwb/kradinf.html](kradzip.zip) file,
for multi-radical search
* [http://kanji.free.fr](kanji.free.fr) database containing kanjis
similarity

If you want to rebuild the database from these sources, just run `make`
in the `utils` directory. This will generate a `kanjis_db` file.

## Requirements

You will need :

* Rubygems (shipped with Ruby >=1.9, need to be installed for earlier
versions)
* Ruby/GTK and Ruby/Libglade

## Installation

`gem build kanjidic.gemspec && sudo gem install kanjidic-0.1.gem`

(see `gem help install` if you want to intall it in your home directory)

## Bugs an missing feature

None in my knowledge, but don't hesitate to fill requests on the Github
[https://github.com/sloonz/kanjidic/issues](tracker).

## LICENCE

See COPYING.
