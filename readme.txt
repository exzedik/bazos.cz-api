Partial release of the "private" bazos.cz API because this whole website is a joke full of scammers and basically pay2sell because most of the categories are flooded by topped listings.
Also get your site together, it's not that expensive to get a designer.
To get access to the full API you'll have to do some debugging yourself (which is surprisingly easy) because I'm too lazy to write these down. Tutorial on how to do this is on the bottom of the page.

get ads - https://www.bazos.cz/api/v1/ads.php?offset={offset}&limit={limit}&section={section}&query={query}&price_from={from}&price_to={to}&sort={sort}
can also search by user (email={email}&phone={phone})
## offset - 0, by increments of 20 (up to 200 but anything else than 20 will likely result in ban)
## limit - 20, by increments of 20 (up to 200 but anything else than 20 will likely result in ban)
    sections:
        &section=XX:
            AU = Auto
            DE = Deti
            DU = Dum a Zahrada
            EL = Elektro
            FO = Foto
            HU = Hudba
            KN = Knihy
            MO = Mobily
            MT = Motorky
            NA = Nabytek
            OB = Obleceni
            PC = PC
            PR = Prace
            RE = Reality
            SL = Sluzby
            SP = Sport
            ST = Stroje
            VS = Vstupenky
            ZV = Zvirata
            OS = Ostatni
    sort types:
        date
        price_asc
        price_desc
        distance:
            must specify:
                &latitude=xx.xxxxxxx&longitude=xx.xxxxxxx

get ratings of user (may require token):
	https://www.bazos.cz/api/v1/ratings.php?offset={offset}&limit={limit}&phone={phone}&email={email}

ad detail:
	https://www.bazos.cz/api/v1/ad-detail-2.php?ad_id={id}&edit=false

to prevent illegal API usage detection:
-do not make fast and repetitive requests
-use these headers:
	user-agent: bazos/2.12.1 (cz.ackee.bazos; build:3582; android {random version}; model:{can be random, preferably android phone}) okhttp/4.8.1
	x-deviceid: {8 digits}
BEWARE OF THIS, YOUR IP MAY GET BLOCKED IF YOU DO NOT PROPERLY IMPLEMENT THESE. I AM NOT RESPONSIBLE IF YOU GET BLOCKED EVEN WHEN USING THESE


To further debug and understand the API:
	1) install the modified apk onto an android device/emulator
	2) download HTTP Toolkit on both your PC and the android device and connect the device to your PC (https://httptoolkit.tech/)
	3) debug
