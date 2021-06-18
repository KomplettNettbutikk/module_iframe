# Hvordan koble opp domene mot din nettbutikk

> Har du ikke domene? Vi anbefaler [domeneshop.no] for en norsk, helproff aktør. Vi får ingenting for å si dette, annet enn fornøyde kunder :-)

## Domeneshop

Før du logger inn på domeneshop så finner du ditt midlertidige domenenavn du har fått fra oss.
Dette er adressen du bruker for å se din demobutikk i dag: f.eks: https://_sc1234.srv7.snartonline.no_/
Uthevet del, altså _sc1234.srv7.snartonline.no_ er ditt midlertidige domenenavn.

1. Logg deg inn på https://domene.shop/login og fyll inn ditt brukernavn og passord.
2. Trykk på *Mine domener* og deretter på ønsket domene.
3. Trykk på fanen *DNS-pekere*, og deretter på *Vis avanserte innstillinger*
4. Du skal opprette 3 pekere og du må trykke på lagre (checkbox til høyre) for hver peker / linje i skjemaet
    1. *Vertsnavn* skal være blankt, velg derettter *TTL* _5 min_, *RR-type* _ANAME_, i *Data* limer du inn ditt midlertidige domene, f.eks. _sc1234.srv7.snartonline.no_
    2. *Vertsnavn* skal være _www_, velg derettter *TTL* _5 min_, *RR-type* _CNAME_, i *Data* limer du inn ditt midlertidige domene, f.eks. _sc1234.srv7.snartonline.no_
    3. *Vertsnavn* skal være blankt, velg derettter *TTL* _5 min_, *RR-type* _TXT_, i *Data* limer du inn _"v=spf1 a mx include:\_spf.domeneshop.no include:\_spf.snartonline.no ~all"_





* PS: Dersom du synes dette er vanskelig, eller allerede har domeneoppsett mot en annen nettside, epost eller liknende kan du ta kontakt med oss for hjelp til riktig oppsett. Dette er kostnadsfritt for førstegangsoppsett. Send i såfall din innloggingsinformasjon og ønsket domenenavn til  [vår utvikler](mailto:mads@komplettnettbutikk.no?subject=Domeneoppsett)
