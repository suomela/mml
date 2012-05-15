Värikorjaus Maanmittauslaitoksen avoimena datana julkaisemille
peruskartoille ("peruskarttarasteri", "painoväriversio").

— — —

Käyttö:

    ./set-palette <alkuperäinen> <uusi>

Esimerkki:

    ./set-palette UL4133L_RVK_1.tif UL4133L_RVK_1.png

Vaatimukset:

    Python
    Python Imaging Library ("easy_install PIL")

— — —

Perusidea

Sekä PDF-muotoisten vektorikarttojen että TIFF-muotoisten
rasterikarttojen vasemmassa ylänurkassa on hyvin pienellä
merkittynä käytetty väripaletti (61 väriä).

Esivalmisteluissa ladataan PDF-muotoinen näytekartta ja kaapataan
siitä väripaletti talteen tiedostoon palette.py.

Värikorjauksessa rasterikartan värit päivitetään rasterikuvan
ylälaidasta löytyvän väripaletin ja tiedoston palette.py ohjaamana.

— — —

Jos haluat luoda tiedoston palette.py uusiksi, aja:

    make clean
    make

Tällöin tarvitaan:

    make
    wget
    ImageMagick
    Ghostscript
    Python
    Python Imaging Library
