# Linuxin asentaminen virtuaalikoneeseen

Tässä osiossa kerron Linuxin asentamisesta virtuaalikoneeseen. En ole aiemmin tehnyt vastaavaa, joten käyn hyvin tarkasti läpi Tero Karvisen ohjeet joka vaiheessa.
<br>
Oma kokoonpanoni on seuraavanlainen:<br>
![Prosessori](https://github.com/vaurasan/h1/blob/main/Prossu.jpg)<br>
![Windows](https://github.com/vaurasan/h1/blob/main/Windows.jpg)<br><br>
Tässä vaiheessa huomaan, että ainakaan minulla nämä kuvat eivät toimi vaikka pitäisi kaiken järjen mukaan. En kuitenkaan siihen tuhlaa enempiä aikoja vaan kirjoitan tietokoneeni specsit tähän tekstinä:(myöhemmin huomasin, että kaikki kuvat toimii, mutta jätän tekstit tähän kuitenkin varmuuden vuoksi)<br>

Suoritin	AMD Ryzen 9 5900X 12-Core Processor 3.70 GHz<br>
Asennettu RAM	32,0 Gt<br>
Järjestelmätyyppi	64-bittinen käyttöjärjestelmä, x64-suoritin<br>
Versio	Windows 11 Pro<br>
Versio	23H2<br>
Käyttöjärjestelmän koontiversio	22631.4037<br>
Käyttökokemus	Windows Feature Experience Pack 1000.22700.1027.0<br><br>


### Debian

Aloitan lataamalla [debian-live-12.6.0-amd64-xfce.iso] tidoston (https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/debian-live-12.6.0-amd64-xfce.iso) omalle koneelleni h1 työkansioon. Tämänhetkinen uusin versio on 12.6.0.<br><br>

### Virtuaalikone

Seuraavaksi lataan Virtualbox virtuaalikoneen osoitteesta: https://www.virtualbox.org/wiki/Downloads.<br>
Alan asentaa virtuaalikonetta asennusohjelmalla, valittuani kohdekansion, asennusohjelma varoittaa, että nettiyhteys katkeaa hetkeksi joten tallennan tämän kirjoitelman varmuuden vuoksi.<br>
![virtuaaliasennus1](https://github.com/user-attachments/assets/ac510f45-e562-40cb-ad25-af098883e1b4)<br>
Varoituksesta huolimatta, pysyn rauhallisena ja jatkan asennusta.<br>
Vaan enpä jatkakaan, kun seuraava herja ilmestyy ruudulle: ![image](https://github.com/user-attachments/assets/b00a48ba-f5b7-4e82-8b70-61d9a7e45162)<br>
Pikainen Googlaus, tai pikemminkin Duckaus tuo minut tälle sivustolle: https://www.sysnettechsolutions.com/en/fix-python-win32api-virtualbox/<br>
Ohjeen mukaan menen python.org/downloads sivulle, josta lataan uusimman Python version 3.12.5.<br>




