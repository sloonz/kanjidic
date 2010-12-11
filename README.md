# Kanjidic
## Presentation

This is a really simple Kanji Dictonary written in Ruby/GTK. It allows
you to find kanjis by:

* Fuzzy skip code
* Multi-radical search
* Similar kanjis

This is achieved by the integration of three different databases :

* The famous kanjidic2.xml file
* kradzip.zip file, for multi-radical search
* kanji.free.fr database containing similar kanjis

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
