---
layout: default
---

# Kaip atblokuoti interneto svetaines

Atblokavimo būdai priklauso nuo blokavimo būdo, bet visi jie iš esmės susiveda į vieną principą:
jeigu valdžia ką nors užblokavo, tai tereikia tiesiog pasirinkti alternatyvų, užkoduotą maršrutą.

## DNS blokavimas

Interneto paslaugos yra surandamos pagal IP adresus - skaičių kratinius, kurie yra patogūs kompiuteriams,
bet žmonėms juos atsiminti sudėtinga. DNS yra sistema, kuri leidžia lengvai atsimenamą pavadinimą
(pvz. `google.com`) pakeisti į IP adresą (pvz. `37.157.151.48`).

Valdžia gali sudaryti adresų sąrašus, kurių negalima naudoti, t.y. DNS negrąžintų atitinkamo
IP adreso ir vartotojo kompiuteris nežinotų į kurį serverį siųsti užklausą.

Toks blokavimas yra tolygus adresų lentelių nuėmimui nuo pastatų, o jo apėjimas yra adresų 
ieškojimas kituose šaltiniuose.

* Normalu:
    - vartotojas serveriui: kur yra www.google.com?
    - DNS serveris vartotojui: 37.157.151.48
* Blokuojama:
    - vartotojas serveriui: kur yra www.google.com?
    - Troll.gov DNS serveris vartotojui: nesakysiu
* Kas naudoja:
    - Estija
    - Belgija
    - Danija
    - Norvegija
    - Švedija
    - Šveicarija
    - Turkija
* Kaip atblokuoti:
    - nemokama, nereikalauja specifinių žinių: nenaudoti oficialių IPT DNS serverių, o naudoti 
      alternatyvius, pvz:
        - Google palaikomi: 8.8.8.8, 8.8.4.4
        - OpenDNS palaikomi: 208.67.222.222, 208.67.220.220, 208.67.222.220, 208.67.220.222
        - Susirask pats: https://www.google.com/search?q=public+dns+servers
        - Instrukcijos: https://www.google.com/search?q=change+dns
    - tinka ir žemiau pateikti sprendimai
* Plačiau:
    - http://en.wikipedia.org/wiki/DNS_blocking

## IP blokavimas

Tam, kad vartotojo kompiuteris galėtų pasiekti nutolusius serverius, duomenų paketas keliauja per
kelis tarpinius taškus, kuriuose galima "sustabdyti" duomenų paketo kelionę link nutolusio IP adreso.

Kadangi kai kurios svetainės gali būti aptarnaujamos iš kelių adresų, o taipogi vienas adresas gali aptarnauti 
kelias svetaines, šis blokavimo būdas ne visada užblokuoja visą "draudžiamą" turinį, o tuo pačiu dažnai 
užblokuoja ir niekuo dėtas svetaines.

Toks blokavimas yra tolygus kelių tarp dviejų taškų griovimui, o jo apėjimas yra keliavimas alternatyviais, 
nors ir lėtesniais, maršrutais.

* Normalu:
    - vartotojas serveriui: ei, 37.157.151.48, parodyk man www.google.com
    - 37.157.151.48 vartotojui: be problemų, ko ieškai?
* Blokuojama:
    - vartotojas serveriui: ei, 37.157.151.48, parodyk man www.google.com
    - Troll.gov MITM serveris: nėra tokio serverio
* Kas naudoja:
    - Argentina
    - Italija
    - Kuba
    - Naujoji Zelandija
    - Pietų Korėja
    - Turkija
* Kaip atblokuoti:
    - visiškai nemokama ir nereikalauja jokių žinių: susisiekti su draugu per Skype ar Hangouts,
      pasidalinti ekranu (screen sharing). Minusas: draugai gali matyti kas vyksta.
    - būna ir nemokamai, nereikalauja jokių techninių žinių: naudoti "internetas į el. paštą" servisus.
      Minusas: ribotas funkcionalumas, veikimo greitis, privatumas.
        - Susirask pats: https://www.google.com/search?q=web+to+email
    - nemokama, nereikalauja specifinių žinių: naudoti proxy serverius. Minusas: veikimas
      gali būti lėtas ir nepatikimas, nederėtų naudoti konfidencialiai informacijai išsiųsti
      ar jungtis prie slaptažodžiu saugomų svetainių.
        - Susirask pats: https://www.google.com/search?q=free+proxy+servers
    - nemokama, nereikalauja specifinių žinių: naudoti pseudo-proxy servisus. Minusas: veikimas
      gali būti lėtas ir nepatikimas, nederėtų naudoti konfidencialiai informacijai išsiųsti
      ar jungtis prie slaptažodžiu saugomų svetainių, gali būti apkrauta reklamomis.
        - Susirask pats: https://www.google.com/search?q=proxy+page
    - nemokama, nereikalauja specifinių žinių: naudoti TOR. Minusas: veikia ypač lėtai, nederėtų
      naudoti konfidencialiai informacijai išsiųsti ar jungtis prie slaptažodžiu saugomų svetainių.
        - https://www.torproject.org
    - mokama, lengvai konfigūruojama: naudoti VPN - užkoduotu būdu prisijungti prie paslaugos serverio,
      o toliau internetas jau matomas iš jo - valdžia nemato kas vyksta iš tikrųjų.
        - Susirask pats: https://www.google.com/search?q=vpn+providers
    - mokama (nebent jau turite nutolusį serverį), reikalauja šiek tiek žinių: naudoti SSH tunelį 
      ("poor man's VPN" - atidaryti užkoduotą kanalą ir į internetą kreiptis per jį).
        - Susirask pats: https://www.google.com/search?q=ssh+tunnel
        - https://github.com/apenwarr/sshuttle
    - mokama (nebent jau turite nutolusį serverį), reiaklauja šiek tiek žinių: naudoti RDP/VNC, t.y.
      prisijungti prie nutolusio kompiuterio ir naudoti jame esančią naršyklę, nesiunčiant tiesioginių
      užklausų "oficialiais" kanalais. Minusas: gali veikti lėtai, nepamiršti užkoduoti ir pačio RDP/VNC
      ryšio.
        - Susirask pats: https://www.google.com/search?q=virtual+desktop+provider
    - mokama, reikalauja techninių žinių: susikurti savo pseudo-proxy servisą. 
      Minusas: derėtų tinkamai apsaugoti, kad nepasinaudotų piktavaliai.
        - Susirask pats: https://www.google.com/search?q=php+proxy+script

## Srauto analizė ir filtravimas

Sudaryti visų interneto šaltinių, kuriuose yra nepageidaujama informacija, sąrašą yra neįmanoma.
Todėl ir blokavimas vien pagal šaltinio adresą ar kelią iki jo yra lengvai apeinamas tiek iš 
informacijos teikėjo, tiek iš informacijos gavėjo pusės. Sudėtingi ir brangūs techniniai sprendimai 
leidžia stebėti visą neužkoduota srautą ir priklausomai nuo jo turinio - automatiškai nutraukti 
duomenų tiekimą. Esminis reikalavimas, kad tokia sistema veiktų - "atplėšinėti" absoliučiai visus 
"laiškus".

* Normalu:
    - vartotojas serveriui: ei, 37.157.151.48, per www.google.com, surask man mielų kačiukų
    - 37.157.151.48 vartotojui: prašom - štai keletas puikių paveiksliukų ir video įrašų
* Blokuojama:
    - vartotojas serveriui: ei, 37.157.151.48, per www.google.com, surask man mielų kačiukų
    - Troll.gov MITM serveris: prašom - štai keletas puikių *ryšys nutrūko*
* Kas naudoja:
    - Bahreinas
    - Iranas
    - Jemenas
    - Jungtiniai Arabų Emyratai
    - Kataras
    - Kinija
    - Kuveitas
    - Omanas
    - Saudo Arabija
    - Sudanas
    - Tunisas
* Kaip atblokuoti:
    - naršyti tik koduotas svetaines (kreiptis išskirtinai per https)
    - nekoduotoms svetainėms naudoti tarpinį koduotą ryšį (kaip ir aukščiau): VPN, SSH tunnel, Tor
    - naudoti kodinius žodžius, keistis informacija abstrakčiais terminais

## Protokolų blokavimas / totalinė kontrolė

Egzistuoja galimybė, kad valdžia visiškai užblokuoja tam tikrus protokolus, ypač tuos,
kurie leidžia komunikaciją koduotais kanalais (VPN, SSH, TLS, RDP). Net nekalbant apie
žmogaus teises toks blokavimas elementariai sužlugytų ekonomiką, nes visi šie protokolai
yra kas dieną naudojami tiek IT profesionalų darbui, tiek automatinei tarp-mašininei komunikacijai,
tiek užtikrinti vidinių verslo duomenų saugumui. Net Kinija to nedaro. Kol kas.

Egipte vykusių 2011 m. protestų metu, internetas buvo išjungtas visiškai. Visiškas atjungimas taipogi
yra taikytas Myanmare, Libijoje, Sirijoje.

Toks blokavimas yra tolygus gyvenimui įkalinimo įstaigoje.

* Normalu:
    - naudotojui prieinami visi protokolai ir duomenys
* Blokuojama:
    - Troll.gov: tau nieko negalima daryti
* Kaip atblokuoti:
    - kurti alternatyvius tinklus, pvz. susisiekti su draugais užsienyje per Skype ar Hangouts ir 
      dalintis ekranu (screen sharing)
    - keistis duomenimis fizinėse laikmenose
    - uždaryti verslą
    - išeiti į gatves
    - emigruoti

# Šaltiniai

* http://www.howtogeek.com/162092/htg-explains-how-the-great-firewall-of-china-works/
* http://en.wikipedia.org/wiki/Internet_censorship_and_surveillance_by_country
* http://en.wikipedia.org/wiki/Internet_censorship_circumvention
* http://www.wikihow.com/Bypass-a-Firewall-or-Internet-Filter
* http://www.howtogeek.com/167418/5-ways-to-bypass-internet-censorship-and-filtering/
* Susirask pats: https://www.google.com/search?q=how+to+bypass+internet+filters
