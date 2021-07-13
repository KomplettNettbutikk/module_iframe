# Mailutsendelse og hvordan unngå å havne i SPAM-mappen
 
Nettbutikken din sender ut mange mail til dine kunder, blant annet ved kunderegistrering, ordre og statusendringer.
 
Slik internett og mail-systemet så kan i utgangspunktet hvem som helst sette din epostadresse som avsender-adresse når de sender ut epost, og på den måten utgi seg for å være deg. Dette er selvfølgelig svært uheldig, og derfor må man ta grep for å unngå dette.
 
Heldigvis finnes det teknologi som hjelper oss med dette, nemlig «Spam/Søppelpost»-mappen. Hvis man kikker innom denne mappen i blant så ser man hvor godt det er å ha den og hvor mye uønsket epost den klarer å filtrere bort.
 
## Legitim epost i SPAM-mappen
Men som du sikkert er vant til fra annen teknologi, så har det sine ulemper også. Noen ganger så er mottakers epost-server overivrig på å filtrere epostboksen, og mailer som kommer fra en legitim avsender (f.eks. din nettbutikk). Hvor «streng» mottakers epost-server er, varierer.

## Hvordan unngå å bli markert som SPAM
For å «overbevise» mottakers epost-server om at mailer fra din nettbutikk er legitime, så har vi i ditt gratis oppsett satt opp en SPF-record i DNS for ditt domene. Ikke vær redd om dette hørtes gresk ut, her kommer forklaring:
Hvis ditt domene er eksempel.no, så går vi inn i innstilligene for ditt domene og så legger vi inn en oppføring som sier at KomplettNettbutikk sin server har lov til å sende mail på vegne av eksempel.no. Inne i denne SPF-recorden så kan det også ligge andre godkjente avsendere. Det kan f.eks. være «outlook.com», «domeneshop.no» eller andre tilbydere du sender epost via. Se dokumentasjon.komplettnettbutikk.no/domene for eksempel på ferdig oppsatt SPF-record.
 
Når epost mottaker-server mottar en epost fra en server som er i SPF-recorden så minsker risikoen for at eposten blir markert som SPAM, da serveren er godkjent.
 
Det er fortsatt mulig at enkelte eposter kan bli markert som SPAM til tross for at oppsettet er 100% rett. Dette har med hvor streng mottaker epost-server er.
 
Innboksen sorterer eposter i faner slik som «Reklame», «Oppdateringer»
I det siste er det kommet funksjonalitet for automatisk sortering av e-postinnboksen. Hotmail/Outlook og Gmail er eksempler på leverandører som sorterer epostene, og funksjonaliteten er automatisk. Avhengig av hvordan sorteringsmekanismene fungerer, så kan eposter fra din nettbutikk havne under  «Primær», «Oppdateringer» eller «Reklame».
Dette er ikke å regne som spam, men kan være forvirrende for kunden, da de må lete flere steder etter eposter fra nettbutikken din.
 

# Blir mailer fortsatt markert som SPAM, eller har du ekstra krav til mail-sikkerhet?
Det finnes en andre og tredje teknologi for å øke mail-sikkerhet og bekjempe spam. Disse heter DKIM (DomainKeys Identified Mail)  og DMARC (Domain-based Message Authentication, Reporting and Conformance).
 
DKIM er en teknikk som legger inn en del av et nøkkel-par i mailen (usynlig for brukerne, men synlig for serverne), samt den andre delen av nøkkelparet i dns-innstillingene for ditt domene. Dette er noe tilsvarende SPF, men er enda sikrere. Det er litt oppsett både på vår server og i dns-innstillinger for ditt domene.
 
DMARC er en instruksjon til mottakers mailserver om hva som skal skje dersom SPF eller DKIM ikke stemmer. Dette kan være: “marker som spam, men motta eposten”, “avvis eposten helt”, “ignorer at noe gikk galt”, “send en rapport om hva som skjedde til epostadressen: eksempel@eksempel.no”.
Det er litt oppsett både på vår server og i dns-innstillinger for ditt domene.
 
Fordeler ved oppsett av DKIM og DMARC
Man benytter all tilgjengelig teknologi for å øke epost-sikkerhet, noe som også kan gjøre det litt mindre sannsynlig at eposter blir markert som spam hos mottaker. Det er imidlertid ingen garantier for mail-levering da vi ikke har kontroll på mottakers epostserver, men med SPF (som du allerede har), DKIM og DMARC så gjør vi alle grep som er tilgjengelig teknisk for at det skal bli så bra som mulig.
 
Ta kontakt med oss for tilbud om oppsett av DKIM og DMARC.

