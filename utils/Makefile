DL_CMD := wget -T30 -t5
KANJI_TGZ_URL := http://kanji.free.fr/download/kanji.tgz
KANJIDIC2_URL := http://www.csse.monash.edu.au/~jwb/kanjidic2/kanjidic2.xml.gz
KRADZIP_URL := ftp://ftp.monash.edu.au/pub/nihongo/kradzip.zip

all: kanjis_db mrproper

kanjis_db: kanji kanjidic2.xml radkfilex
	ruby makedb.rb kanjidic2.xml radkfilex kanji > $@

clean: 
	rm -rf kanji
	rm -f kanjidic2.xml radkfilex

mrproper: clean
	rm -f kanji.tgz  kanjidic2.xml.gz kradzip.zip

kanji: kanji.tgz
	tar xzf $<

kanjidic2.xml: kanjidic2.xml.gz
	gunzip < $< | sed '/<!--.*-->/d' | sed '/<!--/,/-->/d' > $@

radkfilex: kradzip.zip
	unzip $< -d kradzip
	iconv -f EUC-JP -t UTF-8 kradzip/radkfilex > $@
	rm -rf kradzip

download: kanjidic2.xml.gz kanji.tgz kradzip.zip

kanji.tgz: 
	$(DL_CMD) $(KANJI_TGZ_URL) -O $@ || rm -f $@

kanjidic2.xml.gz:
	$(DL_CMD) $(KANJIDIC2_URL) -O $@ || rm -f $@

kradzip.zip: 
	$(DL_CMD) $(KRADZIP_URL) -O $@ || rm -f $@
