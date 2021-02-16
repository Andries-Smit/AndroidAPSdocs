Careportal (bestaat niet meer)
*******************************
De Careportal had dezelfde functies als wat je in Nightscout ziet wanneer je daar op het "+" symbool klikt. Maar careportal gaf geen commando's aan de pomp! Dus als je via de Care Portal een bolus invoerde, dan kreeg je alleen een notitie van de bolus te zien op je Nightscout grafiek. Dit was verwarrend voor veel beginnende loopers.

De code die ervoor zorgde dat de Careportal in AndroidAPS offline kon worden gebruikt, hield bepaalde ontwikkelingen in de AndroidAPS code tegen. **Daarom is besloten om de Careportal te verwijderen uit AAPS versie 2.6.**

De meeste functies van Careportal zijn nog beschikbaar, ze zijn verhuisd naar Acties of naar het Overzichtscherm. Het onderdeel Acties kun je vinden onder het tabblad Acties of in het hamburgermenu (afhankelijk van jouw instellingen in de `Configurator <../Configuration/Config-Builder.html>`_).

Hieronder staat een overzicht van waar je de verschillende functies kunt vinden die voorheen in de Careportal stonden.

Activiteit & feedback
==============================
.. image:: ../images/Careportal_25_26_1_IIb.png
  :alt: Careportal activiteit & feedback
  
* Profiel wissel is verplaatst naar Acties.
* BG controle is verplaatst naar Acties.
* Ouderdom van sensor/canule etc is verplaatst naar Acties.
* Sport is niet langer beschikbaar, maar je kunt het notitie-veld gebruiken dat naar voren komt wanneer je een actie invoert, bijv. (see screenshot in section `carbs & bolus <#carbs-bolus>`__ on this page).

Koolhydraten & bolus
==============================
.. image:: ../images/Careportal_25_26_2_IIa.png
  :alt: Careportal carbs & bolus
  
* Om een bolus te noteren - of het nu gaat om snack, maaltijd of correctie - gebruik de insuline knop op het Overzcht scherm **en let op dat je kiest voor "Geen bolus toedienen, enkel in behandelingen zetten"!**
* Om insuline achteraf in te voeren, d.w.z. om een bolus te registreren die je enige tijd geleden met de pen hebt gegeven, moet je de Insuline knop gebruiken: vink het keuzevakje "Geen bolus toedienen, enkel in behandelingen zetten" aan, en dan verschijnt er een Tijd-veld waar je een negatieve waarde kunt invullen (bijv.

  .. image:: ../images/Careportal_25_26_5.png
    :alt: Achteraf insuline registreren via insuline knop

* Voor koolhydraten correctie gebruik de koolhydraten knop op het Overzicht scherm.
* Tijdelijke basaalstanden kunnen gestart en gestopt worden via Acties. BASAAL" naar "ANNULEER x%" wanneer een tijdelijke basaalstand is ingesteld.

CGM & OpenAPS
==============================
.. image:: ../images/Careportal_25_26_3_IIa.png
  :alt: Careportal CGM & OpenAPS
  
* CGM sensor ingebracht is verplaatst naar Acties.
* Alle andere functies uit deze sectie zijn verwijderd. Je kunt het notitie-veld gebruiken dat naar voren komt wanneer je een actie invoert, bijv. (see screenshot in section `carbs & bolus <#carbs-bolus>`__ on this page).

Pomp
==============================
.. image:: ../images/Careportal_25_26_4_IIb.png
  :alt: Careportal Pomp

* Infuuswissel en insuline ampul wissel is verplaatst naar Acties. Gebruik de knop "ontlucht/vul".
* Pompbatterij wissel is verplaatst naar Acties.
* Pump battery change was moved to actions tab / menu.
