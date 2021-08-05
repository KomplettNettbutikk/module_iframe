# DMARC forklart
Utover SPF (som du trolig allerede har), så finnes det en andre og tredje teknologi for å øke mail-sikkerhet og bekjempe spam. Disse heter DKIM (DomainKeys Identified Mail)  og DMARC (Domain-based Message Authentication, Reporting and Conformance). Vi skal nå se på DMARC.
 
DMARC er en instruksjon til mottakers mailserver om hva som skal skje dersom SPF eller DKIM ikke stemmer. Dette kan være: “marker som spam, men motta eposten”, “avvis eposten helt”, “ignorer at noe gikk galt”, “send en rapport om hva som skjedde til epostadressen: eksempel@eksempel.no”.

## ADVARSLER:
1. Vær 100% sikker på at du har skrevet alt riktig når du oppretter DNS-oppføringer som disse, da de kan gjøre mer skade enn nytte om det blir feil.
2. Vit hva du gjør når du oppretter SPF/DKIM/DMARC. Les dokumentasjon (ikke bare denne, men andre kilder også) nøye, bruk gjerne verktøy for å opprette oppføringer. Vet du ikke 100% sikkert hva disse kodesnuttene gjør, så må du enten finne ut av det, eller droppe å gjøre det, da det potensielt kan føre til at _ingen_ mail kommer frem i en periode etter at du har lagt inn disse kodene. Å rette opp igjen etterpå tar ikke mange minuttene, men de vil ikke _synes_ for mailservere verden rundt før det har gått opp til 24 timer (avhengig av TTL i din dns-oppføring).


## Steg for å opprette DMARC:
1. Logg inn i ditt domenepanel
2. Opprett en ny dns-oppføring med type: TXT
3. Sett _Host/Name/Navn/Subdomene_ til: "_dmarc", slik at full dns blir seende slik ut: "_dmarc.eksempel.no".  NB: uten hermetegnene
4. Sett _value/verdi/innhold/data_ til: "v=DMARC1; p=none;" uten hermetegnene
5. TTL er ikke så nøye, men sett den gjerne så lav som domeneleverandøren din tillater, så slipper du å vente så lenge på oppdatering om du ønsker å gjøre endringer senere.

Du har nå opprettet en DMARC som er instruert til å gjøre _ingenting_.
Hvis du vil ha en masse mail-rapporter (fordi du ønsker å jobbe med å forbedre mail-leveranse), så kan du gå til punkt 4 og endre til (bytt ut _eksempelepost@domene.no_ med en epostadresse du vil bruke for å motta rapportene):
"v=DMARC1; p=none; rua=mailto:eksempelepost@domene.no; ruf=mailto:eksempelepost@domene.no; fo=1"


## Forstå rapportene og jobbe videre
Det er ikke gratis support på å få forklaring på slike rapporter fra KomplettNettbutikk.no, men dersom du ønsker at vi skal jobbe med din epost så kan vi gjøre dette på oppdrag.

Hvis du vil se på dette selv så kan du finne mye nyttig informasjon f.eks. her:
https://mxtoolbox.com/. De har også verktøy for å analysere rapportene, og generere nye DMARC-records for å begynne å filtrere bort uønsket mail, som er det neste naturlige steget om du ønsker 100% perfekt mail-oppsett. 

## Siste steg når du har analysert rapportene over tid
Når du har sett på rapportene over tid, samlet data og sett at alt fungerer fint (i korte trekk at det kun er faktiske spam-meldinger som det kommer rapporter om) så kan du gå videre til å sette uønskede eposter i karantene eller avvise dem.

### Karantene-modus gjøres slik:
Endre følgende del av DMARC-oppføringen fra: "p=none;" til "p=quarantine;"

### Avvis-modus gjøres slik:
Endre følgende del av DMARC-oppføringen fra: "p=quarantine;" til "p=reject;"
