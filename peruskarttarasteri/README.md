Värikorjaus Maanmittauslaitoksen peruskartoille
===============================================

Värikorjaus Maanmittauslaitoksen [avoimena datana][1] julkaisemalle [peruskarttarasteriaineistolle][2].

[<img width="400" height="400" src="https://github.com/suomela/mml/raw/master/peruskarttarasteri/examples/old.png" alt="Vanha" title="Vanha">][3]
[<img width="400" height="400" src="https://github.com/suomela/mml/raw/master/peruskarttarasteri/examples/new.png" alt="Uusi" title="Uusi">][4]

(sisältää Maanmittauslaitoksen peruskarttarasteriaineistoa 05/2012 – [lisenssi][5])

[1]: http://www.maanmittauslaitos.fi/avoindata/hankinta
[2]: http://www.maanmittauslaitos.fi/digituotteet/peruskarttarasteri
[3]: https://github.com/suomela/mml/raw/master/peruskarttarasteri/examples/old.png
[4]: https://github.com/suomela/mml/raw/master/peruskarttarasteri/examples/new.png
[5]: http://www.maanmittauslaitos.fi/avoindata_lisenssi_versio1_20120501


Käyttö
------

Käyttö:

    ./set-palette <alkuperäinen> <uusi>

Esimerkki:

    ./set-palette UL4133L_RVK_1.tif UL4133L_RVK_1.png

Vaatimukset:

- Python
- [Python Imaging Library][6] — asennus: easy_install PIL

[6]: http://www.pythonware.com/library/pil/


Perusidea
---------

Sekä PDF-muotoisten vektorikarttojen että TIFF-muotoisten
rasterikarttojen vasemmassa ylänurkassa on hyvin pienellä
merkittynä käytetty väripaletti (61 väriä).

Esivalmisteluissa ladataan PDF-muotoinen näytekartta ja kaapataan
siitä väripaletti talteen tiedostoon `palette.py`.

Värikorjauksessa rasterikartan värit päivitetään rasterikuvan
ylälaidasta löytyvän väripaletin ja tiedoston `palette.py` ohjaamana.
Tässä voidaan hyödyntää 61-värisestä paletista vain 60 väriä, sillä
rasterikonversiossa on kaksi väriä korvattu samalla.

Jos haluat luoda tiedoston palette.py uusiksi, aja:

    make clean
    make

Tällöin tarvitaan:

- make
- wget
- ImageMagick
- Ghostscript
- Python
- Python Imaging Library


Säätövaraa
----------

Varsinaisesti väripaletin määrää se, miten Ghostscript konvertoi
PDF-tiedoston värit PNG-kuvan väreiksi. Tähän voi vaikuttaa
Ghostscriptin valitsimilla.

Tiedostoa `palette.py` voi toki editoida käsinkin…
