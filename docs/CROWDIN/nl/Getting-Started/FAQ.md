# Veelgestelde vragen

Om vragen toe te voegen aan de Veelgestelde Vragen: volg deze [instructies](../make-a-PR.md)

# Algemeen

## Kan ik de AndroidAPS app gewoon downloaden?

Nee. Er is geen downloadbaar apk bestand voor AndroidAPS. Je moet het zelf [bouwen](../Installing-AndroidAPS/Building-APK.md). Omdat:

AndroidAPS wordt gebruikt om je pomp te bedienen en insuline te geven. Volgens de huidige Europese regelgeving vallen dit soort systemen onder klasse IIa of IIb voor medische hulpmiddelen. Dat betekent dat die een wettelijke goedkeuring (CE-markering) vereisen, waarvoor verschillende studies en verificaties nodig zijn. Het verspreiden van een ongereguleerd medisch hulpmiddel is illegaal. In andere delen van de wereld bestaat vergelijkbare regelgeving.

Deze regelgeving beperkt zich niet tot verkoop (in de zin dat er geld voor wordt gevraagd), maar is van toepassing op elke vorm van distributie (zelfs gratis weggeven). Het bouwen van een medisch apparaat voor jouzelf is de enige manier om niet onder deze regelgeving te vallen.

Dat is waarom een kant-en-klare app niet verspreid mag worden.


## Hoe begin ik?
Ten eerste, moet je alle **fysieke onderdelen van een closed loop** verzamelen:

* A [supported insulin pump](./Pump-Choices.md),
* een [Android smartphone](Phones.md) (Apple iOS wordt niet ondersteund door AndroidAPS - je kunt wel [iOS Loop](https://loopkit.github.io/loopdocs/) gebruiken) en
* een [glucose sensor](../Configuration/BG-Source.rst).

Ten tweede, moet je de **fysieke onderdelen instellen**. Zie het [gebruiksvoorbeeld](Sample-Setup.md) met stap voor stap instructies.

Ten derde, moet je alle **software bouwen en instellen**: AndroidAPS en CGM/FGM bron.

Ten vierde moet je leren en **begrijpen hoe het algoritme is ontworpen om jouw behandel instellingen** correct in te kunnen stellen. Het grondbeginsel van closed loopen is dat jouw basaalstanden en koolhydraatratio's correct zijn.  All recommendations assume that your basal needs are met and any peaks or troughs you're seeing are a result of other factors which therefore require some one-off adjustments (exercise, stress etc.).  De aanpassingen die de closed loop kan maken zijn uit veiligheid beperkt (zie maximaal toegestane basaalstand in [OpenAPS Reference Design](https://openaps.org/reference-design/)). Dit betekent dat je de closed loop niet moet inzetten om een fout afgestelde basaalstand te verhelpen. Wanneer je bijvoorbeeld vaak een lage waarde hebt vlak voor een maaltijd, dan moet waarschijnlijk je basaal omlaag.  You can use [autotune](https://openaps.readthedocs.io/en/latest/docs/Customize-Iterate/autotune.html#phase-c-running-autotune-for-suggested-adjustments-without-an-openaps-rig) to consider a large pool of data to suggest whether and how basals and/or ISF need to be adjusted, and also whether carb ratio needs to be changed.  Or you can test and set your basal the [old fashioned way](https://integrateddiabetes.com/basal-testing/).

## Zijn er nog praktische tips?

### Wachtwoordbeveiliging
Als je niet wilt dat jouw instellingen gemakkelijk worden aangepast, dan kun je het instellingen menu voorzien van een wachtwoord. Ga naar "Wachtwoord voor instellingen" in het instellingen menu en typ een zelfgekozen wachtwoord. De volgende keer dat je het instellingen menu opent, moet je het wachtwoord intypen om verder te kunnen. Wanneer je later geen wachtwoord meer wilt gebruiken, ga dan naar het "Wachtwoord voor instellingen" veld en verwijder de tekst.

### Android Wear Smartwatches
Wanneer je in de toekomst de Android Wear app wilt gebruiken om vanaf een smartwatch te kunnen bolussen of instellingen te wijzigen, dan moet je instellen dat notificaties van AndroidAPS niet geblokkeerd worden. Bevestiging van opdrachten die je op je smartwatch invoert, komen namelijk via een notificatie binnen op je telefoon.

### Pomp afkoppelen
Als je je pomp afkoppelt voor douchen/in bad gaan/zwemmen/sport etc. dan moet je dit aan AndroidAPS laten weten, zodat jouw IOB waarde blijft kloppen met de werkelijkheid.
* Houd de knop 'Closed Loop' linksbovenaan het Overzicht scherm lang ingedrukt (NB: wanneer je nog niet in closed loop modus zit, zal hier 'Open Loop' staan).
* Selecteer **"Verbreek verbinding XXmin/u met pomp"**
* Hiermee zet je de basaal op nul voor de tijdsduur die je hebt gekozen.
* De minimale lengte van de tijd voor een onderbreking is afhankelijk van de minimale lengte van TBRs die op jouw pomp kan worden ingesteld. Dus, als je wilt loskoppelen voor een kortere periode, dan kies je voor de kortst beschikbare periode voor jouw pomp. Vervolgens koppel de pomp handmatig terug aan zoals hieronder beschreven.
* De knop 'Closed Loop' (of 'Open Loop') zal rood worden en de tekst 'Verbinding verbroken(xx m)' wordt weergegeven.
* AAPS zal de pomp automatisch opnieuw verbinden nadat de aangegeven tijd is verstreken en de closed loop zal opnieuw beginnen te werken.

   ![Pomp afkoppelen](../images/PumpDisconnect.png)

* Als je jouw pomp weer wilt aankoppelen voordat de aangegeven tijd is verstreken, kun je de verbinding handmatig herstellen.
* Houd de rode knop 'Verbinding verbroken (xx m)' lang ingedrukt.
* Selecteer 'Opnieuw verbinden met pomp'

   ![Opnieuw verbinden met pomp](../images/PumpReconnect.png)

### Aanbevelingen niet alleen gebaseerd op één enkele CGM-waarde
For safety, recommendations made are based on not one CGM reading but the average delta.  Therefore, if you miss some readings it may take a while after getting data back before AndroidAPS kicks in looping again.

### Leestips
Er zijn verschillende blogs met goede tips om jou te helpen om de loop goed in te stellen (in het Engels):
  * [Fine-tuning Settings](https://seemycgm.com/2017/10/29/fine-tuning-settings/) See my CGM
  * [Why DIA matters](https://seemycgm.com/2017/08/09/why-dia-matters/) See my CGM
  * [Limiting meal spikes](https://diyps.org/2016/07/11/picture-this-how-to-do-eating-soon-mode/) #DIYPS
  * [Hormones and autosens](https://seemycgm.com/2017/06/06/hormones-2/) See my CGM

## Welke spullen moet ik bij me hebben voor noodgevallen?
Allereerst, je moet dezelfde spullen bij je hebben als iedere andere persoon die een insulinepomp gebruikt. Als aanvulling daarop, wordt voor mensen die loopen met AndroidAPS aanbevolen om de volgende extra dingen bij je of binnen handbereik te hebben:

* Losse accu (powerbank) zodat je je smartphone, smartwatch en (wellicht) bluetooth reader kunt opladen
* Digitale backup (Dropbox, Google Drive, ...) van de apps die je gebruikt, zoals jouw meest recente AndroidAPS apk-bestand en jouw key store (digitale handtekening), AndroidAPS instellingenbestand, xDrip instellingenbestand, aangepaste Dexcom app, ...
* Batterijen voor je insulinepomp

## Hoe zorg ik dat de CGM/FSL goed blijft vastzitten?
Je kunt hem vastplakken: er zijn op maat gemaakte 'fixeerpleisters' voor veelgebruikte CGM-systemen verkrijgbaar. Some loopers use the cheaper standard kinesiology tape or rocktape.

Er bestaan ook speciale bandjes voor om je bovenarm die de CGM/FGM op zijn plek houden. Die zijn online verkrijgbaar (even googelen).

# AndroidAPS instellingen

The following list aims to help you optimize settings. It may be best to start at the top and work to the bottom. Aim to get one setting right before changing another. Work in small steps rather than making large changes at once. You can use [Autotune](https://autotuneweb.azurewebsites.net/) to guide your thinking, although it should not be followed blindly: it may not work well for you or in all circumstances. Note that settings interact with one another - you can have 'wrong' settings that work well together in some circumstances (e.g. if a too-high basal happens to be at the same time as a too-high CR) but do not in others. This means that you need to consider all the settings and check they work together in a variety of circumstances.

## Duur van insuline activiteit (DIA)
### Beschrijving & testen
De tijd die het duurt totdat de concentratie insuline is afgenomen naar nul.

This is quite often set too short. Dit wordt door veel mensen te kort ingesteld. Dit zou je op ten minste 5 uur moeten zetten, mogelijk 6 of 7.
### Invloed op BG
Te korte DIA kan zorgen voor te lage BGs. En omgekeerd.

Als DIA te kort is, denkt AAPS te vroeg dat je eerdere bolus helemaal is uitgewerkt, en, bij hoog blijvende glucosewaardes, zal hij je meer insuline gaan geven. (Eigenlijk wacht AAPS niet zo lang, maar voorspelt wat er zou gebeuren en blijft hij insuline toevoegen). Dit zorgt voor “insuline-stapeling” waarvan AAPS zich niet bewust is.

Voorbeeld van een te korte DIA is een hoge BG gevolgd door een overcorrectie en daarmee een te lage BG.

## Basaalstanden (E/uur)
### Beschrijving & testen
De hoeveelheid insuline die nodig is om jouw BG stabiel te houden.

Test jouw basaalstanden door te 'open loopen' en te vasten. Start met jouw basaaltest 5 uur na je laatste voedsel+bolus, en bekijk vanaf dat moment hoe jouw BG verandert. Repeat a few times.

Als BG daalt, is je basaalstand te hoog. En omgekeerd.
### Invloed op BG
Te hoge basaal kan leiden tot lage BGs. En omgekeerd.

AAPS houdt jouw ingestelde basaalstanden aan als 'nullijn'. Als je basaal te hoog is, zal hij een 'zero temp' (basaalstand van 0) als een te sterke negatieve IOB meetellen. Als reactie op die negatieve IOB zal AAPS meer correcties geven dan hij zou moeten doen, vanwege de neiging om jouw IOB naar nul te willen brengen.

Dus een te hoge basaal zal lage BGs creëren: zowel door de ingestelde standaardbasaal die je krijgt, als door de correctie-insuline die AAPS geeft om het streefdoel te bereiken.

Omgekeerd kan een te lage basaal leiden tot hoge BGs en zal het AAPS niet lukken om je omlaag te brengen naar het streefdoel.

## Insuline gevoeligheids factor (Insulin Sensitivity Factor, ISF) (mmol/l/E of mg/dl/E)
### Beschrijving & testen
Hoeveel jouw BG zou moeten dalen na het nemen van 1E insuline.

Zorg dat je eerst jouw basaal goed hebt ingesteld, daarna kun je ISF testen door AAPS op 'open loop' te zetten bij een vlakke BG, terwijl IOB nul is en je geen voedsel in je maag hebt. Neem dan een paar glucose tabletten zodat je BG op een plateau van een hogere waarde komt.

Neem vervolgens een hoeveelheid insuline (op basis van jouw huidige ISF) om naar jouw streefBG te komen.

Be careful as this is quite often set too low. Too low means 1 U will drop BG faster than expected.
### Invloed op BG
**Lagere ISF** = een kleinere daling van BGs voor elke eenheid insuline (wordt ook wel ‘heftiger / agressiever’ of ‘sterker’ genoemd). Een te lage ISF zal leiden tot lage BGs.

**Hogere ISF** = een grotere daling in BGs voor elke eenheid insuline (wordt ook wel ‘minder sterk / minder agressief’ of ‘zwakker’ genoemd). Een te hoge ISF kan leiden tot hoge BGs.

**Voorbeeld:**
* BG is 190 mg/dl (10,5 mmol/l) en het streefdoel is 100 mg/dl (5,6 mmol/l).
* Dus, je wilt correctie van 90 mg/dl (= 190-110).
* ISF = 30 -> 90/30 = 3 eenheden insuline
* ISF = 45 -> 90/45 = 2 eenheden insuline

Een ISF die te laag is (niet ongebruikelijk) kan leiden tot ‘overcorrecties’, omdat AAPS denkt dat meer insuline nodig is om een hoge BG te corrigeren dan dat hij feitelijk nodig heeft. Dit kan leiden tot een "golfbeweging / achtbaan" in je glucosegrafiek (vooral tijdens vasten). In deze omstandigheden moet je je ISF verhogen. Dit betekent dat AAPS kleinere correctie doses zal geven, en dit voorkomt dat een hoge BG wordt overgecorrigeerd met daarna een lage BG.

Omgekeerd kan een ISF die te hoog is, leiden tot ondercorrectie, wat betekent dat jouw BG boven het streefdoel blijft – met name zichtbaar gedurende de nacht.

## Koolhydraat ratio (KH) (g/E)
### Beschrijving & testen
Hoeveel gram koolhydraten jij kunt eten voor 1E insuline.

Je zult ook wel de Engelse afkortingen I:C ratio (Insulin to Carb ratio) of CR (Carb Ratio) tegenkomen.

Zorg dat je eerst jouw basaal + ISF goed hebt ingesteld, daarna kun je CR testen door AAPS op 'open loop' te zetten, op een moment dat IOB nul is en je geen voedsel in je maag hebt. Neem dan een maaltijd waarvan je de koolhydraten precies weet, en injecteer een hoeveelheid insuline op basis van je huidige KH ratio. Je kunt bij deze test het beste kiezen voor voedsel dat je normaal gesproken ook zou eten rond dat tijdstip. En zorg dat je het aantal koolhydraten exact weet (pak weegschaal + koolhydratentabel erbij).

> **Opmerking:** 
> 
> In sommige Europese landen werden/worden broodeenheden (ookwel: broodwaarden of koolhydraten porties) gebruikt om te berekenen hoeveel insuline nodig is voor een bepaalde hoeveelheid voedsel. Hierbij staat 1 broodeenheid gelijk aan een vaste hoeveelheid koolhydraten. In Duitsland werd/wordt 12 of 10 gram koolhydraten gebruikt voor 1 broodeenheid, in België wordt vaak gerekend met 1 broodeenheid = 12,5 gram koolhydraten.
> 
> Bij gebruik van broodenheden is de hoeveelheid koolhydraten een vast getal, waarbij de hoeveelheid insuline varieert per persoon. ("Hoeveel insuline is nodig voor één broodeenheid?")
> 
> Bij gebruik van KH ratio's (insuline:koolhydraat ratio's) is de hoeveelheid insuline een vast getal, en de hoeveelheid koolhydraten varieert per persoon. ("Hoeveel gram koolhydraten kan iemand eten bij één eenheid insuline?")
> 
> Voorbeeld:
> 
> Broodeenheid factor (BE = 12,5g koolhydraten): 2,4 E/BE -> Je hebt 2,4 eenheden insuline nodig wanneer je één brood-eenheid eet.
> 
> Bijbehorende KH ratio: 12,5/2,4 = 5,2 g/E -> je kunt 5,2g koolhydraten eten bij één eenheid insuline.
> 
> BE factor 2,4E /12,5g ===> KH ratio = 12,5g/2,4E = 5,2 g/E
> 
> Conversietabellen zijn online beschikbaar, bijvoorbeeld [ hier ](https://www.mylife-diabetescare.com/files/media/03_Documents/11_Software/FAS/SOF_FAS_App_KI-Verha%CC%88ltnis_MSTR-DE-AT-CH.pdf) (in het Duitse systeem.

### Invloed op BG
**Lagere KH ratio** = minder voedsel per eenheid. Oftewel je gebruikt meer insuline voor dezelfde hoeveelheid koolhydraten. Can also be called ‘more aggressive’.

**Hogere KH ratio** = meer voedsel per eenheid. Oftewel je gebruikt minder insuline voor dezelfde hoeveelheid koolhydraten. Kan ook ‘minder agressief’ worden genoemd.

Als jouw BG hoger uitkomt nadat een maaltijd is verteerd en IOB weer is teruggekomen naar nul, dan is jouw KH ratio te groot. En omgekeerd: als je BG lager uitkomt, dan is KH ratio te klein.

# APS algoritme
## Waarom zie ik "dia:3" in de "OPENAPS AMA"-tab ook al heb ik een andere DIA in mijn profiel?

![AMA 3u](../images/Screenshot_AMA3h.png)

In AMA betekent "dia" niet de "Duur van Insuline Actie". Het is een parameter die vroeger wel gelinkt was aan de DIA. Nu betekent het 'binnen welke tijd zou de correctie moeten zijn afgerond'. En heeft het niets meer te maken met de berekening van de IOB. In OpenAPS SMB wordt deze parameter niet meer gebruikt.

## Profiel

### Waarom minimaal een 5 uur DIA (Duur van Insuline Actie) gebruiken in plaats van 2-3 uur?
Well explained in [this article](https://www.diabettech.com/insulin/why-we-are-regularly-wrong-in-the-duration-of-insulin-action-dia-times-we-use-and-why-it-matters/). Vergeet niet om op `ACTIVEER PROFIEL` te klikken na het wijzigen van je DIA.

### Waarom zorgt de loop ervoor dat mijn bloedsuiker vaak zo ver zakt dat ik een hypo krijg, terwijl mijn COB (koolhydraten aan boord) nul is?
First of all, check your basal rate and make a no-carb basal rate test. If it is correct, this behavior is typically caused by a too low ISF. Een typisch voorbeeld van een te lage ISF ziet er zo uit:

![ISF te laag](../images/isf.jpg)

### Waarom heb ik hoge glucosepieken na een maaltijd terwijl ik een closed loop gebruik?
First of all, check your basal rate and make a no-carb basal rate test. If it is correct and your BG is falling to your target after carbs are fully absorbed, try to set an 'eating soon' temp target in AndroidAPS some time before the meal or think about an appropriate prebolus time with your endocrinologist. If your BG is too high after the meal and still too high after carbs are fully absorbed, think about decreasing your IC with your endocrinologist.  Wanneer je bloedglucose te hoog is terwijl je nog COB hebt, en je te laag uitkomt nadat alle koolhydraten geabsorbeerd zijn, dan kun je vragen aan je behandelaars of je jouw KH ratio kunt verhogen én een bepaalde hoeveelheid tijd te nemen tussen bolus en maaltijd.

# Overige instellingen

## Nightscout instellingen

### AndroidAPS NSClient zegt 'Not allowed' (niet toegestaan) en wil geen gegevens uploaden. Wat kan ik doen?
Controleer 'Verbindingsinstellingen' in NSClient. Misschien heb je geen wifi verbinding of je hebt 'Enkel tijdens opladen' geactiveerd en jouw oplaadkabel is niet aangesloten.

## CGM instellingen

### Waarom zegt AndroidAPS dat 'de gekozen BG bron geen optimale filtering toepast'?
Als je een andere CGM/FGM dan Dexcom G5 en G6 in xDrip Native-modus gebruikt, dan krijg je deze waarschuwing in het OpenAPS-tabblad. Zie [Filteren van glucosewaardes](../Usage/Smoothing-Blood-Glucose-Data-in-xDrip.md) voor meer informatie.

## Pomp

### Waar moet ik mijn pomp dragen?
Er zijn talloze mogelijkheden om de pomp te dragen. Het maakt niet uit of je loop gebruikt of niet.

### Batterijen
Bij loopen kan de pompbatterij sneller leegraken dan bij normaal gebruik, omdat je telefoon veel vaker interactie heeft met de pomp dan een normale gebruiker zou hebben.  We raden aan om de batterij al te vervangen als hij nog voor 25% vol is, omdat communicatie tussen telefoon en pomp dan al achteruit kan gaan.  Je kunt een batterij-alarm in Nightscout instellen, door de variabele PUMP_WARN_BATT_P in te stellen.  Tips om de levensduur van de batterij te verlengen:
* de tijd dat het LCD-scherm van de pomp aan staat, verkorten (in instellingen menu van de pomp)
* de tijd dat de achtergrondverlichting van het beeldscherm aan staat, verkorten (in instellingen menu van de pomp)
* stel meldingen in op geluid in plaats van trillen (in instellingen menu van de pomp)
* gebruik de knoppen van de pomp alleen bij het vullen van de pomp. Bekijk alle andere informatie op je telefoon (batterijduur, reservoir inhoud, geschiedenis etc).
* op sommige telefoons wordt AndroidAPS app vaak afgesloten om de batterij of het RAM geheugen te besparen. Elke keer dat AndroidAPS dan weer opnieuw wordt gestart, maakt je telefoon weer verbinding met de pomp om opnieuw de bolus geschiedenis en huidige basaalstand uit te lezen vanuit het pompgeheugen. This consumes battery. Om te zien of dit gebeurt, ga naar Instellingen > NSClient en schakel 'Log app start naar NS' in. Nightscout will receive an event at every restart of AndroidAPS, which makes it easy to track the issue.  To reduce this happening, whitelist AndroidAPS app in the phone battery settings to stop the app power monitor closing it down.

   Bijvoorbeeld, om dit in te stellen op een Samsung telefoon met Android Pie:
   * Ga naar Instellingen-> Apparaatonderhoud-> Batterij
   * Scroll totdat je AndroidAPS tegenkomt en tik op AndroidAPS
   * Schakel de optie "Zet app op spaarstand" uit
   * OOK ga je naar Instellingen -> Apps -> (Drie cirkel symbool in de rechterbovenhoek van het scherm), selecteer "bijzondere toegang" -> het Optimaliseren van het gebruik van de batterij
   * Scroll naar AndroidAPS en zorg ervoor dat deze niet geselecteerd is.

* maak de contactpunten van de batterij schoon met een alcoholdoekje, om te voorkomen dat er nog vet of olie van het productieproces is achtergebleven.
* for [Dana R/RS pumps](../Configuration/DanaRS-Insulin-Pump.md) the startup procedure draws a high current across the battery to purposefully break the passivation film (prevents loss of energy whilst in storage) but it doesn't always work to break it 100%.  Either remove and reinsert battery 2-3 times until it does show 100% on screen, or use battery key to briefly short circuit battery before insertion by applying to both terminals for a split second.
* bekijk meer tips over [specifieke soorten batterijen](../Usage/Accu-Chek-Combo-Tips-for-Basic-usage#battery-type-and-causes-of-short-battery-life) voor de Combo-pomp

### Verwisselen van reservoirs en canules
Wisselen van het reservoir kan niet worden gedaan via AndroidAPS, maar moet gedaan worden rechtstreeks via de pomp, zoals beschreven in de handleiding van de pompfabrikant.
* Houd "Open Loop" / "Closed Loop" op het Overzicht-scherm van AndroidAPS lang ingedrukt en selecteer 'Verbreek verbinding 1u met pomp'
* Koppel nu de pomp af en verwissel het reservoir volgens de instructies van de pompfabrikant.
* Het vullen van de slang en canule kan rechtstreeks op de pomp worden gedaan. Gebruik in dit geval de [ONTLUCHT / VUL knop](../Usage/CPbefore26#pump) op het tabblad Acties om aan AAPS te laten weten dat je het reservoir of de canule hebt verwisseld.
* Wanneer je daarmee klaar bent, koppel je de pomp weer aan en houd 'Verbinding verbroken (.. m)' lang ingedrukt.

Het 'Ontlucht/vul' scherm van AAPS gebruikt niet de functie van "prime infusie set" van de pomp, maar vult de infuusset en/of canule met behulp van een bolus die niet in de geschiedenis van AAPS verschijnt. Dit betekent dat een lopende tijdelijke basaalstand niet zal worden onderbroken.  Selecteer op het Acties (Act) tabblad de knop [ONTLUCHT / VUL](../Usage/CPbefore26#pump) en kies de hoeveelheid insuline die nodig is om de infuusset/canule te vullen en druk op OK. Wanneer er nog lucht in de infuusset zit, herhaal de vorige stap.  Je kunt standaardhoeveelheden instellen in Instellingen > Andere > Vul standaard hoeveelheid.  Hoeveel eenheden nodig zijn staat in het instructieboekje in de doos met infuussets, dit verschilt per type infuusset en is afhankelijk van de lengte van de canule en de lengte van de slang.

## Achtergrond

Je vindt de AndroidAPS achtergrond voor je telefoon op de [telefoons pagina](../Getting-Started/Phones#phone-background).

## Dagelijks gebruik

### Hygiëne

#### Wat te doen tijdens het douchen?
Je kunt de pomp afkoppelen bij het douchen. Voor deze korte tijd kun je meestal wel zonder je pomp. Maar je moet AAPS wel laten weten dat je de pomp loskoppelt, zodat de IOB berekeningen blijven kloppen.

Zie de [ beschrijving hierboven ](../Getting-Started/FAQ#disconnect-pump).

### Werk
Depending on the kind of your job, maybe you use different treatment factors on workdays. As a looper you should think of a [profile switch](../Usage/Profiles.md) for your estimated working day (e.g. more than 100% for 8h when sitting around or less than 100% when you are active), a high or low temporary target or a [time shift of your profile](../Usage/Profiles#time-shift) when standing up much earlier or later than regular. Wanneer je [Nightscout profielen](../Configuration/Config-Builder#ns-profile) gebruikt, kun je ook een specifiek profiel (bijv. 'thuis' of 'werkdag') aanmaken, en dagelijks het profiel activeren dat je op dat moment nodig hebt.

## Vrije tijd

### Sporten
Je moet je oude gewoontes uit de pre-loop tijd afleren. Als je simpelweg evenveel extra koolhydraten neemt als voorheen bij het sporten, dan zal het systeem voor deze koolhydraten gaan corrigeren waarmee hun effect teniet wordt gedaan.

Wat je wilt is dat je extra koolhydraten kunt nemen, zonder dat de loop daarvoor de bijbehorende hoeveelheid insuline toedient.

Probeer daarvoor deze stappen:
* Stel een [Profiel wissel ](../Usage/Profiles.md) in kleiner dan 100%.
* Stel een [Tijdelijk streefdoel voor Activiteit](../Usage/temptarget#activity-temp-target) in dat hoger ligt dan jouw normale streefdoel.
* Als je SMB gebruikt, zorg er dan voor dat ["Gebruik SMB met een hoog tijdelijk streefdoel"](../Usage/Open-APS-features#enable-smb-with-high-temp-targets) en ["Activeer SMB altijd"](../Usage/Open-APS-features#enable-smb-always) zijn uitgeschakeld.

Pre- and postprocessing of these settings is important. Make the changes in time before sport and consider the effect of muscle filling.

Als je op vaste tijden vaste activiteiten doet, (bijvoorbeeld een klasje in de sportschool) kun je overwegen om [Automatisering](../Usage/Automation.rst) voor een Profiel wissel en Tijdelijk streefdoel te gebruiken. Je kunt de Automatisering ook op basis van GPS locatie instellen, maar dat maakt het timen voorafgaand aan sporten wel lastiger.

Het exacte percentage van de Profiel wissel, de waarde voor het Tijdelijke streefdoel en de timing van al deze instellingen zijn voor iedereen anders. Begin aan de veilige kant als je op zoek gaat naar de juiste waarde voor jou (start met een lager percentage en hoger streefdoel).

### Sex
Je kunt de pomp loskoppelen voor wat 'vrijheid', maar je moet AAPS wel vertellen dat je dat doet. Zodat jouw IOB juist wordt berekend.

Zie de [ beschrijving hierboven ](../Getting-Started/FAQ#disconnect-pump).

### Alcohol
Alcohol drinken in de closed loop modus heeft als risico dat het algoritme niet goed kan voorspellen welke invloed de alcohol heeft op jouw bloedglucose. Je zult voor jezelf een manier moeten vinden om hiermee om te gaan. AndroidAPS heeft verschillende functies die je hierbij kunt gebruiken:

* De closed loop uitschakelen en je diabetes handmatig onder controle houden
* Een hoger tijdelijk streefdoel instellen en onaangekondigde maaltijden (UAM, UnAnnounced Meals) uitschakelen, om te voorkomen dat je extra IOB krijgt toegediend
* een profielwissel, naar beduidend minder dan 100%

Bij het drinken van alcohol moet je altijd je CGM in de gaten houden, om op tijd wat koolydraten te nemen en zo een hypo te kunnen voorkomen.

### Slapen

#### Hoe kan ik 's nachts closed loopen zonder mobiele of WIFI straling?
Veel gebruikers zetten 's nachts hun telefoon in vliegtuigmodus. Wanneer je wilt dat de loop werkt in vliegtuigmodus, volg dan deze stappen (dit werkt alleen als je een locale BG-bron hebt zoals xDrip+ of de gepatchte Dexcom app, het werkt NIET wanneer jouw BG-waardes via Nightscout binnenkomen):

1. Zet de telefoon in vliegtuigmodus.
2. Wacht totdat de vliegtuigmodus actief is.
3. Schakel Bluetooth in.

Je kunt nu niet bellen of gebeld worden, en je bent ook niet verbonden met internet. Maar de closed loop werkt nog wel.

Sommige mensen hebben problemen met lokale uitzendingen ontdekt (AAPS ontvangt geen BG-waarden van xDrip +) wanneer de telefoon in vliegtuigmodus is. Ga naar Instellingen > Inter-app-instellingen > Identificatie-ontvanger en geef `info.nightscout.androidaps` op.

![xDrip + Basic Inter-app Instellingen Ontvanger identificeren](../images/xDrip_InterApp_NS.png)


### Reizen

#### Hoe kan ik wisselen van tijdzone?
Met DanaR en DanaR Koreaans hoef je niets te doen. Zie voor andere pompen de [wisselen van tijdzone](../Usage/Timezone-traveling.md) pagina voor meer details.

## Arts en diabetesverpleegkundige

### Ziekenhuis
Wanneer je jouw behandelaar informatie wilt geven over AndroidAPS en doe-het-zelf loopen, dan kun je de [Informatie voor zorgverleners/behandelaars](../Resources/clinician-guide-to-AndroidAPS.md) uitprinten.

### Afspraak met je internist of diabetesverpleegkundige

#### Rapporten
Je kunt rapporten op jouw nightscout site (https://YOUR-NS-SITE.com/report) laten zien tijdens jouw afspraak, of gebruik [Nightscout Reporter](https://nightscout-reporter.zreptil.de/).
