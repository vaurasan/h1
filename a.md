# Linuxin asentaminen virtuaalikoneeseen

Tässä osiossa kerron Linuxin asentamisesta virtuaalikoneeseen. En ole aiemmin tehnyt vastaavaa, joten käyn hyvin tarkasti läpi Tero Karvisen ohjeet joka vaiheessa.
<br>
Oma kokoonpanoni on seuraavanlainen:<br>
![Prosessori](https://github.com/vaurasan/h1/blob/main/Prossu.jpg)<br>
![Windows](https://github.com/vaurasan/h1/blob/main/Windows.jpg)<br>
(huom. kokeilin ensin Teron tapaa tuoda kuvia tänne, mutta kun se ei toiminut aloin oikomaan kuvakaappaustyökalulla ctrl+c, ctrl+v:tä hyväksi käyttäen, tällaiselle aloittelijalle huomattavasti nopeampi tapa, mutta toki hyvä olisi osata molemmat)<br><br>
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
![virtuaaliasennus1](https://github.com/user-attachments/assets/ac510f45-e562-40cb-ad25-af098883e1b4)<br><br>

Varoituksesta huolimatta, pysyn rauhallisena ja jatkan asennusta.<br>
Vaan enpä jatkakaan, kun seuraava herja ilmestyy ruudulle: ![image](https://github.com/user-attachments/assets/b00a48ba-f5b7-4e82-8b70-61d9a7e45162)<br><br>

Pikainen Googlaus, tai pikemminkin Duckaus tuo minut tälle sivustolle: https://www.sysnettechsolutions.com/en/fix-python-win32api-virtualbox/<br>
Ohjetta noudattaen, menen python.org/downloads sivulle, josta lataan uusimman Python version 3.12.5 ja suoritan asennustiedoston järjestelmänvalvojana.<br>
Tämän jälkeen step 3:n mukaan avaan PowerShellin järjestelmänvalvojana ja kirjoitan komentoriville: py -m pip install pywin32.<br>
Seuraavanlainen virhe tapahtuu: ![pywinerror](https://github.com/user-attachments/assets/83189454-fb08-4546-97e6-4eed0cfa7cdc)<br><br>

Kokeilen poistaa ja uudelleenasentaa Pythonin koneeltani samaisella asennusohjelmalla, jonka juuri latasin. Nyt uudestaan PowerShelliin ja sama litania komentoriville, ja homma onnistui ![image](https://github.com/user-attachments/assets/a48ed366-5d0e-41ce-86ef-de30cb69b10b)<br><br>

Tässä vaiheessa vaaditaan tietokoneen uudelleenkäynnistys, joten teen sen.<br>
Nyt takaisin PowerShelliin järjestelmänvalvojana ja komentoriville ohjeen mukaan: python.exe -m pip install --upgrade pip.<br>
Tulee virheilmoitus: ![image](https://github.com/user-attachments/assets/86624cb7-33ff-4b7d-a2e7-1bbf380dc686)<br>
Tästä huolimatta yritän nyt asentaa Virtualboxia ja hämmästyksekseni ei enää tule samaa herjaa mikä tuli aiemmin, asennus menee läpi muitta mutkitta.<br>

Seuraavaksi virtuaalikoneen luontiin.<br>
Teron ohjeiden mukaan ylävalikosta Machine - New, aukeaa luonti-ikkuna, valitaan Expert Mode ja aletaan syöttämään haluttuja tietoja:<br>
Jostain syystä en pysty laittamaan täppää kohtaan Skip Unattended Installation, pakko mennä näillä korteilla mitkä on jaettu.<br>
![image](https://github.com/user-attachments/assets/b45aa78e-ce67-4bf9-9b92-b52b9c407e46)<br><br>

Ohjeen mukaan Hardwareen Base Memory 4000MB. Sitten Create Virtual Hard Disk Now ja laitetaan Size 60GB. Valitaan VDI (VirtualBox Disk Image) ja painetaan Finish. Nyt näkyy vasemmalla luotu virtuaalikone offline-tilassa.<br>![image](https://github.com/user-attachments/assets/83ad21c7-b954-4a9a-bfa7-3fe352ff58fd)
<br>

## Linuxin asentaminen juuri luotuun virtuaalikoneeseen

- Valitaan virtuaalikone aktiiviseksi vasemmalta ja mennään Settings.<br>
- Storage välilehti auki, Controller: IDE-kohdasta valitaan CDROM Empty.<br>
- Optical Drive kohtaan haetaan CD-levyn kuvaketta klikkaamalla Virtual Optical Disk File ja haetaan aiemmin ladattu debian-live-12.6.0-amd64-xfce Linuxin  asennusohjelma ja painetaan Choose. Nyt meillä on virtuaalikone ja virtuaalinen CD syötetty koneeseen sisälle.<br>


