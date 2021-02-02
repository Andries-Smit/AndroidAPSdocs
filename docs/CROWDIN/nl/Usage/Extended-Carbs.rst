Vertraagde koolhydraten / "eCarbs"
**************************************************
Bij reguliere pomptherapie zijn vertraagde bolussen / multiwave bolussen handig voor vette maaltijden (pizza, pasta, pannenkoeken etc) die je bloedglucose lange tijd laten stijgen, langer dan de insuline bij een normale bolus werkzaam zou zijn. In een closed loop is dat echter niet zo zinvol (en geeft het technische problemen) omdat vertraagde/multiwave bolussen door de pomp worden uitgevoerd als een langdurige en vooraf gedefinieerde hoge basaal. Voor meer informatie, zie `vertraagde bolus <../Usage/Extended-Carbs.html#vertraagde-bolus>`_ hieronder.

The need to deal with such meals still exists though. Daarom is in AndroidAPS vanaf versie 2.0 een optie ingebouwd die "eCarbs" heet.

eCarbs zijn koolhydraten die over meerdere uren worden uitgespreid. Voor standaard maaltijden met meer koolhydraten dan vet/eiwit, is het gebruik van eCarbs niet persé nodig.  Anders zou (zeker bij gebruik van SMB) de IOB veel te snel oplopen terwijl de maaltijd je BG slechts langzaam laat stijgen, met een hypo als resultaat. Met deze informatie kan de loop geleidelijk aan SMB's afgeven om die koolhydraten aan te pakken.

Het nut van eCarbs is niet beperkt tot vette / eiwitrijke maaltijden. Ze zijn ook handig als door andere invloeden de bloedglucose gedurende meerdere uren flink stijgt, bijvoorbeeld bij medicijnen zoals corticosteroïden.

Vul de duur in, het aantal koolhydraten en desgewenst een timeshift.

.. image:: ../images/eCarbs_Dialog.png
  :alt: Koolhydraten invoeren

En je ziet de 25 gram koolhydraten bij COB staan, tussen haakjes omdat het toekomstige koolhydraten zijn:

.. image:: ../images/eCarbs_Graph.png
  :alt: eCarbs in grafiek

Op de Behandelingen tab zie je koolhydraten staan, ze zijn donker oranje omdat ze in de toekomst zijn:

.. image:: ../images/eCarbs_Treatment.png
  :alt: vertraagde koolhydraten in de Behandelingen tab


-----

Hoe je vertraagde koolhydraten gebruikt voor een maaltijd met vet en eiwit wordt hier beschreven: `https://adriansloop.blogspot.co.at/2018/04/page-margin-0.html <https://adriansloop.blogspot.co.at/2018/04/page-margin-0.html>`_

-----

Voor onderstaand voorbeeld wordt aangeraden om OpenAPS SMB APS te gebruiken, met SMB ingeschakeld en de instelling SMB met koolhydraten ingeschakeld te hebben.

A scenario e.g. Neem nou bijvoorbeeld een pizza, daarbij kun je een gedeeltelijke bolus voor de maaltijd via de bolus calculator geven en via de knop koolhydraten de resterende koolhydraten gedurende 4 a 6 uur, te laten beginnen na 1 of 2 uur. Je zult natuurlijk moeten uitproberen welke precieze waarden voor jou werken. Hierbij kun je ook (in kleine, verstandige stapjes) variëren met de instelling 'max aantal minuten basaal om de SMB te limiteren tot' om het algoritme agressiever/minder agressief te laten zijn.
Voor maaltijden met nauwelijks koolhydraten en een hoog vet/eiwitgehalte kan het genoeg zijn om alleen eCarbs te gebruiken en geen bolus (zie de blogpost hierboven).

Iedere keer dat je eCarbs invoert, wordt er in jouw Careportal automatisch een opmerking toegevoegd.

Vertraagde bolus
==================================================
Zoals hierboven vermeld, werken vertraagde of multiwave bolussen niet echt in een closed loop. `See below <../Usage/Extended-Carbs.html#why-extended-boluses-won-t-work-in-a-closed-loop-environment>`_ for details

Vertraagde bolus en overschakelen naar open loop - alleen voor Dana en Insight pomp
-----------------------------------------------------------------------------
Sommige mensen wilden dolgraag een optie hebben om een vertraagde bolus te kunnen gebruiken in AAPS omdat ze voor bepaalde voedingsmiddelen willen bolussen zoals ze eerder gewend waren. 

Daarom is er vanaf versie 2.6 een optie voor een vertraagde bolus toegevoegd, deze werkt alleen met Dana en Insight pompen. 

* De closed loop zal automatisch worden onderbroken en er wordt overgeschakeld naar open loop modus nadat de vertraagde bolus functie is geactiveerd. 
* Bolus eenheden, resterende en totale tijd zullen worden weergegeven op het Overzicht-scherm.
* NB: Op de Insight pomp is de vertraagde bolus optie *niet beschikbaar* als `TBR emulatie <../Configuration/Accu-Chek-Insight-Pump.html#settings-in-aaps>`_ is ingeschakeld. 

.. image:: ../images/ExtendedBolus2_6.png
  :alt: vertraagde bolus in AAPS 2.6

Waarom vertraagde bolussen niet werken in een closed loop
----------------------------------------------------------------------------------------------------
1. The loop determines that now 1.55U/h is to be delivered. Whether this is delivered as an extended bolus or TBR does not matter to the algorithm. In fact, some of the pumps use the extended bolus. What should happen then? Most pump drivers then stop the extended bolus -> You didn't even need to start it.
2. If you had the extended bolus as input, what should happen in the model?

   1. Should it be considered neutral together with the BR and looped on it? Then the loop should also be able to reduce the bolus if, for example, you get too low and all the "neutral" insulin is taken away?
   2. Should the extended bolus simply be added? So the loop should simply be allowed to continue? Even in the worst hypo? I don't think this is so good: A hypo is foreseen but it must not be prevented?
   
3. The IOB that the extended bolus builds up materializes after 5 minutes at the next run. Accordingly, the loop would give less basal. So not much changes... except that the possibility of hypo avoidance is taken.
