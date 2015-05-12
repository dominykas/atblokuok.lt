---
layout: default
---

# Kaip filtruojamas interneto turinys

## DNS blokavimas

* Normalu:
    - vartotojas serveriui: kur yra www.google.com?
    - DNS serveris vartotojui: 37.157.151.48
* Blokuojama:
    - vartotojas serveriui: kur yra www.google.com?
    - Troll government DNS serveris vartotojui: nesakysiu
* Kas naudoja:
    - Estija
* Kaip atblokuoti:
    - nemokama ir paprasta: nenaudoti oficialių IPT DNS serverių, o naudoti alternatyvius, pvz:
        - Google palaikomi: 8.8.8.8, 8.8.4.4
        - OpenDNS: 208.67.222.222, 208.67.220.220, 208.67.222.220, 208.67.220.222
        - Susirask pats: https://www.google.com/search?q=public+dns+servers
        - Instrukcijos: TODO
* Plačiau:
    - http://en.wikipedia.org/wiki/DNS_blocking

## IP blokavimas

* Normalu:
    - vartotojas serveriui: ei, 37.157.151.48, parodyk man www.google.com
    - 37.157.151.48 vartotojui: be problemų, ko ieškai?
* Blokuojama:
    - vartotojas serveriui: ei, 37.157.151.48, parodyk man www.google.com
    - Troll government MITM serveris: nėra tokio serverio
* Kas naudoja:
    - TODO
* Kaip atblokuoti:
    - nemokama ir paprasta (bet lėta): naudoti proxy serverius
        - Susirask pats: https://www.google.com/search?q=free+proxy+servers
    - TOR
    - VPN
    - SSH tunnel

## Srauto analizė ir filtravimas

TODO

## Protokolų blokavimas / totalinė kontrolė

Egzistuoja galimybė, kad valdžia visiškai užblokuoja tam tikrus protokolus, ypač tuos,
kurie leidžia komunikaciją koduotais kanalais (VPN, SSH, TLS, RDP). Net nekalbant apie
žmogaus teises toks blokavimas elementariai sužlugytų ekonomiką, nes būtų tolygus
vien atvirlaiškių siuntinėjimui. Net Kinija to nedaro.

* Normalu:
    - naudotojui prieinami visi protokolai ir duomenys
* Blokuojama:
    - Troll government: tau nieko negalima daryti
* Kaip atblokuoti:
    - kurti alternatyvius tinklus
    - uždaryti verslą
    - išeiti į gatves
    - emigruoti

# Šaltiniai

* http://www.howtogeek.com/162092/htg-explains-how-the-great-firewall-of-china-works/
* en.wikipedia.org/wiki/Internet_censorship_and_surveillance_by_country
