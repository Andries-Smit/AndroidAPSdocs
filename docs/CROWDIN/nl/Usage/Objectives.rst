Doelen
**************************************************

AndroidAPS heeft een reeks leerdoelen die je moet doorlopen, zodat je alle opties en instellingen leert kennen om veilig te kunnen loopen.  De leerdoelen zorgen ervoor dat je alles goed hebt ingesteld, en dat je snapt wat het systeem doet en waarom.

Als je een **andere telefoon gaat gebruiken**, dan kun je jouw `instellingen exporteren <../Usage/ExportImportSettings.html>`_ om je voortgang door de doelstellingen te behouden. Ook jouw veiligheidsinstellingen zoals max.  Wanneer je je instellingen niet exporteert en importeert op je nieuwe telefoon, dan zul je weer helemaal opnieuw moeten beginnen met de leerdoelen.  Het is een goed idee om regelmatig een `back-up te maken van jouw instellingen <../Usage/ExportImportSettings.html>`_ voor het geval dat er iets met jouw telefoon gebeurt.

Als je wilt teruggaan in de doelen, zie de `uitleg hieronder <../Usage/Objectives.html#teruggaan-in-doelen>`_.
 
Doel 1: Instellen van visualisatie en monitoring en analyseren van basaal en ratio's
====================================================================================================
* Selecteer de bloedglucose bron die jij gebruikt.  Zie `BG Source <../Configuration/BG-Source.html>`_ voor meer informatie.
* Selecteer de juiste pomp in Configurator (Selecteer 'virtuele pomp' als je een pomp gebruikt waar geen AndroidAPS driver voor bestaat) om ervoor te zorgen dat jouw pomp kan communiceren met AndroidAPS.  
* Als je de DanaR pomp gebruikt, volg dan de `DanaR <../Configuration/DanaR-Insulin-Pump.html>`_ instructies om de pomp te koppelen aan AndroidAPS.
* Volg de instructies van de `Nightscout <../Installing-AndroidAPS/Nightscout.html>`_ pagina om ervoor te zorgen dat Nightscout gegevens kan ontvangen en weergeven.
* Note that URL in NSClient must be **WITHOUT /api/v1/** at the end - see `NSClient settings in Preferences <../Configuration/Preferences.html#nsclient>`__.

*Het kan zijn dat je even moet wachten tot de volgende bloedglucose-waarde binnenkomt voordat AndroidAPS de wijzigingen opmerkt.*

Doel 2: Leer hoe AndroidAPS te gebruiken
==================================================
* Voer verschillende acties uit in AndroidAPS zoals beschreven in dit doel.
* Klik op de oranje tekst "Nog niet voltooid" om toegang te krijgen tot de opdrachten.
* Er staan links naar deze wiki om je op weg te helpen in het geval je de specifieke actie nog niet kent.

  .. image:: ../images/Objective2_V2_5.png
    :alt: Screenshot doel 2

Doel 3: Bewijs jouw kennis
==================================================
* Zorg dat je slaagt voor de multiple-choice test van jouw AndroidAPS kennis.
* Klik op de oranje tekst "Nog niet voltooid" om toegang te krijgen tot de pagina met de vraag en antwoordopties.

  .. image:: ../images/Objective3_V2_5.png
    :alt: Screenshot doel 3

* Er staan links naar deze wiki om je op weg te helpen als je het antwoord niet meteen weet.
* De vragen voor doelstelling 3 voor AAPS versie 2.8 zijn volledig herschreven door gebruikers van wie Engels de moedertaal is, en vervolgens vertaald naar o.a. De vernieuwde vragen gaan grotendeels over dezelfde inhoud, en er zijn een paar nieuwe vragen toegevoegd.
* Voor mensen die de vragen uit Doel 3 in een vorige versie hadden afgerond, is Doel 3 weer op 'nog niet voltooid' komen te staan omdat deze nieuwe vragen nog beantwoord moeten worden.
* Voor hen geldt dat zij niet aan een nieuw Doel kunnen beginnen totdat ze de nieuwe vragen ook beantwoord hebben. Het is wel verstandig om er binnenkort mee aan de slag te gaan; wanneer een volgende versie uitkomt, die wellicht nieuwe functies (en bijbehorende nieuwe Doelen) heeft, dan zou je niet aan een nieuw Doel kunnen beginnen totdat je alle vragen hebt beantwoord.

Doel 4: Beginnen met een open loop
==================================================
* Selecteer Closed-Loop vanuit het `Instellingen-menu <../Configuration/Preferences.html>`_ of door de Loop-knop linksbovenin het Overzicht-scherm ingedrukt te houden.
* Work through the `Preferences <../Configuration/Preferences.html>`__ to set up for you.
* Voer minstens 20 tijdelijke basaalstanden in over een periode van 7 dagen; voer ze in op jouw pomp en bevestig in AndroidAPS dat je ze hebt geaccepteerd.  Controleer dat deze gegevens zichtbaar zijn in AndroidAPS en Nightscout.
* Stel `tijdelijke streefdoelen <../Usage/temptarget.html>`_ in indien nodig. Gebruik bijvoorbeeld een tijdelijk hypo streefdoel om te voorkomen dat het systeem te sterk corrigeert voor een stijgende bloedsuiker na een hypo. 

Verminder het aantal meldingen
--------------------------------------------------
Doe dit bijvoorbeeld door bredere streefdoelen in te stellen, zoals 90-150 mg/dl of 5,0-8,5 mmol/l.
* Voor 's nachts zou je de bovengrens van je streefdoel flink kunnen verhogen (of de Open Loop zelfs helemaal kunnen deactiveren) voor een ongestoorde nachtrust. 
* Daarnaast kun je in de Instellingen een groter getal invullen bij "Minimale verzoek voor aanpassing[%]".

  .. image:: ../images/OpenLoop_MinimalRequestChange2.png
    :alt: Open Loop Minimale verzoek voor aanpassing
     
* En uiteraard kun je ervoor kiezen om niet elke 5 minuten alle suggesties daadwerkelijk uit te voeren...

Doel 5: De Open Loop begrijpen, inclusief de voorgestelde tijdelijke basaalstanden
====================================================================================================
Kijk naar de `determine basal logic <https://openaps.readthedocs.io/en/latest/docs/While%20You%20Wait%20For%20Gear/Understand-determine-basal.html>`_ en naar de `voorspelling in de glucosegrafiek van het AndroidAPS Overzichts-scherm <../Getting-Started/Screenshots.html#voorspellingslijnen>`_ of Nightscout, en naar de berekening in je OpenAPS tab.
 
Je wilt beginnen met een streefdoel dat hoger is dan normaal, totdat je vertrouwen in de berekeningen en de instellingen hebt gekregen.  Het systeem staat toe

* een laag streefdoel tot minimaal 4 mmol/l (72 mg/dl) of maximaal 10 mmol/l (180 mg/dl) 
* een hoog streefdoel tot minimaal 5 mmol/l (90 mg/dl) of maximaal 15 mmol/l (225 mg/dl)
* een enkele waarde als tijdelijk streefdoel tussen 4 mmol/l en 15 mmol/l (72 mg/dl tot 225 mg/dl)

Het streefdoel is de waarde waar de berekeningen op zijn gebaseerd, en is niet hetzelfde als waar je jouw bloedglucose waarden binnen wilt houden.  Als je een erg brede range als streefdoel instelt, bijvoorbeeld een verschil van 3 mmol/l of meer (50 mg/dl of meer), dan zul je zien dat AAPS niet vaak in actie komt. Dit komt omdat de voorspelde bloedglucose meestal binnen dat brede bereik zal liggen en het systeem dus niet vaak een andere tijdelijk basaal voorstelt. 

Je kunt experimenteren met je lage en hoge streefdoel en een nauwer bereik instellen, bijvoorbeeld 1 of minder mmol/l (20 mg/dl of minder) verschil, en observeren hoe het systeem daardoor zijn gedrag aanpast.  

You can view a wider range (green lines) on the graph for the values you aim to keep your blood glucose within by entering different values in `Preferences <../Configuration/Preferences.html>`__ > Range for Visualisation.
 
.. image:: ../images/sign_stop.png
  :alt: Stop-teken

Stop hier als je een virtuele pomp gebruikt en in Open Loop wilt blijven - klik NIET op Verificatie aan het einde van dit doel.
------------------------------------------------------------------------------------------------------------------------------------------------------

.. image:: ../images/blank.png
  :alt: blanco

Doel 6: Starten in Closed Loop met bescherming tegen lage BG
====================================================================================================
.. image:: ../images/sign_warning.png
  :alt: Waarschuwings-teken
  
De closed loop zal hoge glucosewaarden in doel 6 niet naar beneden kunnen brengen, omdat in dit doel alleen nog de 'pompstop voor laag' functie geactiveerd is. Om hoge glucosewaarden naar beneden te krijgen, moet je zelf nog handmatig ingrijpen!
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
* Selecteer Open-Loop vanuit het Instellingen-menu of door de Open Loop / Closed Loop -knop linksbovenin het Overzicht-scherm ingedrukt te houden.
* Stel je lage en hoge streefdoel iets hoger in dan je normaal zou doen, voor de zekerheid.
* Kijk hoe tijdelijke basaastanden worden ingesteld door te kijken naar de blauwe tekst in het Overzicht-scherm, of door het blauwe deel van de grafiek op het Overzicht-scherm te bekijken.
* Zorg dat jouw instellingen zo zijn, dat AndroidAPS in 5 dagen tijd niet heeft hoeven ingrijpen om een lage glucosewaarde te voorkomen.  Mocht je op dit moment nog veelvuldige of heftige lage glucosewaardes hebben, dan moet je waarschijnlijk nog iets verbeteren aan jouw instellingen van DIA, basaal, ISF of KH ratio (in die volgorde).
* Je hoeft je instellingen niet te veranderen. Tijdens doel 6 wordt de maxIOB automatisch door het systeem op nul gezet in de berekeningen. Deze beperking verdwijnt als je naar doel 7 gaat.
Dit betekent dat bij een dalende glucosewaarde de basaalstand naar beneden wordt aangepast, maar bij een stijgende glucosewaarde er alleen maar een hogere basaalstand wordt ingesteld wanneer de IOB negatief is (IOB kan negatief zijn, als hij eerder al een lagere basaalstand heeft ingesteld ivm lage glucosewaarde).  

  .. image:: ../images/Objective6_negIOB.png
    :alt: Voorbeeld negatieve IOB

* Als jouw basaal IOB negatief is (zie screenshot hierboven) kan AndroidAPS een tijdelijk basaal > 100% instellen.
* You may temporarily experience spikes following treated hypos without the ability to increase basal on the rebound.

Doel 7: Inregelen van de closed loop, verhoog de max IOB boven 0 en laat geleidelijk de streef BG dalen
====================================================================================================
Verhoog jouw 'Max totaal IOB dat OpenAPS niet kan overschrijden' (in OpenAPS heet dit 'max-iob') naar een getal groter dan 0.

  Deze aanbeveling moet als uitgangspunt worden beschouwd. Als je op de 3x zit en je ziet dat het systeem de neiging heeft om jouw bloedglucose te laag uit te laten komen, pas dan deze instelling aan naar een lager getal. If you are very resistant raise it a very little at a time.

  .. image:: ../images/MaxDailyBasal2.png
    :alt: max dagelijkse basaal

* Once confident on how much IOB suits your looping patterns then reduce your targets to your desired level.


Doel 8: Pas basaalstanden en de ratio's aan indien nodig, activeer hierna de Autosens optie
====================================================================================================
* Je kunt `Autotune <https://openaps.readthedocs.io/en/latest/docs/Customize-Iterate/autotune.html>`_ gebruiken om eenmalig te laten berekenen of jouw basaalstanden goed zijn ingesteld, of een traditionele basaaltest doen.
* Schakel `Autosens <../Usage/Open-APS-features.html>`_ in gedurende een periode van 7 dagen en bekijk de witte lijn in de grafiek op het Overzichts-scherm. en houd op de OpenAPS tab in de gaten hoe AndroidAPS de basaalstanden en/of streefdoelen dienovereenkomstig aanpast.

*Don’t forget to record your looping in* `this form <https://bit.ly/nowlooping>`_ *logging AndroidAPS as your type of DIY loop software, if you have not already done so.*


Doel 9: Probeer extra functies voor gebruik overdag en krijg vertrouwen in jouw closed loop systeem
====================================================================================================
* Vóór de AAPS versie 2.7 was maaltijd assist (MA) het basisalgoritme voor AAPS en je moest doel 8 hebben afgerond om `advanced meal assist (AMA) <../Usage/Open-APS-features.html#geavanceeerde-maaltijdhulp-ama>`_ te activeren.
* Omdat `advanced meal assist (AMA) <../Usage/Open-APS-features.html#geavanceerde-maaltijdhulp-ama>`_ inmiddels het standaard algoritme is bij AAPS versie 2.7, kun je de komende 28 dagen gebruiken om functies uit te proberen die je nog niet hebt gebruikt en om meer vertrouwen te krijgen in je gesloten loop systeem.


Doel 10: Activeren van extra functies overdag zoals SMB (Super Micro Bolus)
====================================================================================================
Je moet het `SMB hoofdstuk in deze wiki <../Usage/Open-APS-features.html#super-micro-bolus-smb>`_ en het `hoofdstuk oref1 in openAPSdocs <https://openaps.readthedocs.io/en/latest/docs/Customize-Iterate/oref1.html>`_ lezen om te begrijpen hoe SMB werkt, met name het idee achter de tijdelijke basaalstanden van nul (zero-temp).
* Daarna kun je `maxIOB verhogen <../Usage/Open-APS-features.html#maximum-total-iob-openaps-cant-go-over-openaps-max-iob>`_ zodat SMB goed kan functioneren. maxIOB bevat nu alle IOB, niet alleen de toegediende basale insuline. Als je een bolus van 8E geeft voor een maaltijd en jouw maxIOB is 7E, dan zullen er geen SMBs worden afgegeven totdat IOB onder de 7E komt.
Wanneer je van AMA naar SMB wisselt, dan moet je jouw instelling voor min_5m_carbimpact in de Opname instellingen veranderen van 3 naar 8. Je moet dit handmatig doen wanneer je van AMA naar SMB wisselt.


Doel 11: Automatisering
====================================================================================================
* Je moet Doel 11 starten om `Automatisering <../Usage/Automation.html>`_ te kunnen gebruiken.
* Zorg ervoor dat je alle doelen hebt voltooid, inclusief het `examen <../Usage/Objectives.html#doel-3-bewijs-jouw-kennis>`_.
* Het behalen van eerdere doelen zal geen effect hebben op andere doelen die je al hebt behaald. Je behoudt alle reeds afgeronde doelen!


Teruggaan in doelen
====================================================================================================
Als je om welke reden dan ook terug wilt gaan in de leerdoelen druk dan op "voltooiing wissen".

.. image:: ../images/Objective_ClearFinished.png
  :alt: Teruggaan in doelen
