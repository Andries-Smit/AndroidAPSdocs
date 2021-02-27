AAO apskaičiavimas
**************************************************

Kaip AndroidAPS apskaičiuoja AAO reikšmes?
==================================================

Oref1
--------------------------------------------------

Neįsisavinti angliavandeniai yra nebeskaičiuojami po nustatyto laiko

.. image:: ../images/cob_oref0_orange_II.png
  :alt: Oref1

AAPS, SvertinisVidurkis
--------------------------------------------------

absorption is calculated to have ``COB == 0`` after specified time

.. image:: ../images/cob_aaps2_orange_II.png
  :alt: AAPS, SvertinisVidurkis

Jei minimalus angliavandenių įsisavinimas (min_5m_carbimpact) yra naudojamas vietoj reikšmių, apskaičiuotų iš KG svyravimų, atsiranda oranžinis taškas AAO grafike.

Neteisingų AAO reikšmių aptikimas
==================================================

AAPS įspėja jus, jei jūs ketinate bolusuoti su AAO iš prieš tai buvusio valgio ir algoritmas mano, kad dabartinis AAO apskaičiavimas gali būti neteisingas. Šiuo atveju jis duos jums papildomą užuominą patvirtinimo ekrane, kai pasinaudosite boluso patarėju. 

Kaip AndroidAPS nustato klaidingas AAO reikšmes? 
--------------------------------------------------

Įprastai AAPS nustato angliavandenių įsisavinimą pagal KG svyravimus. Tuo atveju, jei jūs suvedėte angliavandenius, bet AAPS nemato numatyto jų įsisavinimo pagal KG svyravimus, ji naudos `min_5m_carbimpact <../Configuration/Config-Builder.html?highlight=min_5m_carbimpact#absorption-settings>`_ metodą apskaičiuoti įsisavinimui (taip vadinamą 'atsarginę priemonę'). Kadangi šis metodas skaičiuoja tik minimalų angliavandenių įsisavinimą nekreipiant dėmesio į KG svyravimus, tai gali lemti neteisingas AAO reikšmes.

.. image:: ../images/Calculator_SlowCarbAbsorbtion.png
  :alt: Užuomina apie neteisingą AAO reikšmę

In the screenshot above, 41% of time the carb absorption was mathematically calculated by the min_5m_carbimpact instead of the value  detected from deviations.  Tai reiškia, kad gal jūsų turite mažiau aktyvių angliavandenių organizme nei apskaičiuota algoritmo. 

Kaip elgtis su tokiu įspėjimu? 
--------------------------------------------------

- Apsvarstykite veiksmų atšaukimą - paspauskite Atšaukti vietoj OK.
- Dar kartą apskaičiuokite jūsų būsimą valgį su bolus patarėju paliekant AAO nepažymėtą.
- Jei esate tikri, kad jums reikia korekcinio boluso, įveskite jį rankiniu būdu.
- Bet kokiu atveju būkite atsargūs, kad neperdozuotumėte!

Kodėl algoritmas nenustato AAO teisingai? 
--------------------------------------------------

- Gal jūs pervertinote angliavandenius juos suvedant.  
- Aktyvumas / pratimai po prieš tai buvusio valgio
- I:A reikalinga patikslinti
- klaidinga min_5m_carbimpact reikšmė (rekomenduojama 8 su SMB, 3 su AMA)

Įvestų angliavandenių koregavimas rankiniu būdu
==================================================
Jei pervertinote ar nepakankamai įvertinote angliavandenių kiekį, galite juos ištaisyti naudodamiesi terapijos skirtuku ir Veiksmų portalu, kaip aprašyta `čia <../Getting-Started/Screenshots.html#carb-correction>`_.
