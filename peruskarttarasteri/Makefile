.PHONY: clean

palette.py: crop.png get-palette
	./get-palette $< $@

crop.png: sample.png
	convert -crop 125x1+0+1 $< $@

sample.png: sample.pdf
	gs -sDEVICE=png16m -r254 -o $@ $<

sample.pdf:
	# http://www.maanmittauslaitos.fi/aineistot-palvelut/digitaaliset-tuotteet/nayteaineistot/peruskarttarasteri
	wget -O $@ 'http://www.maanmittauslaitos.fi/sites/default/files/UL4424R_RVK.pdf'

clean:
	rm -f sample.pdf sample.pmg crop.png palette.py
