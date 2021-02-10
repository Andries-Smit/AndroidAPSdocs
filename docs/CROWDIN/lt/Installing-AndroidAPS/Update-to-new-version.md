# Atnaujinimas į naują versiją arba atšaką

## Kurti sau, o ne parsisiųsti

**Dėl reikalavimų medicininiams įrenginiams, nėra galimybės tiesiog parsisiųsti AndroidAPS programą. Programos kūrimas savo reikmėms yra visiškai teisėtas, tačiau jums neleidžiama perduoti jos kopijos kitiems! Žr. [DUK](../Getting-Started/FAQ.md) dėl išsamesnės informacijos.**

## Svarbios pastabos

* Prašome atnaujinti kuo greičiau, kai tik nauja versija yra prieinama. Gausite [informaciją AndroidAPS pagrindiniame ekrane](../Installing-AndroidAPS/Releasenotes#release-notes) apie naują versiją.
* Nuo versijos 2.3 jūs turite naudoti git atnaujinimui. Atnaujinimas per zip failą daugiau nebeveikia.
* Versijos 2.7 duomenų saugyklos adresas pakeistas į <https://github.com/nightscout/AndroidAPS>. Jei nesate susipažinę su git, paprasčiausias būdas yra pašalinti esamą AndroidAPS katalogą ir pradėti [programos kūrimą nuo pradžių](../Installing-AndroidAPS/Building-APK.md).
* Please use [Android Studio Version 4.1.1](https://developer.android.com/studio/) or newer to build the apk.
* [Windows 10 32-bit systems](../Installing-AndroidAPS/troubleshooting_androidstudio#unable-to-start-daemon-process) are not supported by Android Studio 4.1.1.
* Jei naudojate xDrip įsitikinkite, kad [nustatote gavėją](../Configuration/xdrip#identify-receiver).
* Jei naudojate Dexcom G6 su [modifikuota Dexcom programa](../Hardware/DexcomG6#if-using-g6-with-patched-dexcom-app), jums reikės versijos iš [2.4 aplanko](https://github.com/dexcomapp/dexcomapp/tree/master/2.4).

## Trumpas vadovas patyrusiems vartotojams

Prašau praleiskite šį punktą, jeigu atnaujinate pirmą kartą. Trumpas vadovas patyrusiems vartotojams. Kitas jūsų žingsnis būtų [įdiegti git](../Installing-AndroidAPS/git-install.rst), jei dar to nepadarėte.

Jei jau atnaujinote AAPS ankstesnėje versijoje ir naudojate Windows kompiuterį, galite atlikti atnaujinimą keturiais paprastais žingsniais:

1. [Export your settings](../Usage/ExportImportSettings#export-settings) from the existing AAPS version on your phone to be on the save side
2. [Atnaujinkite vietinę kopiją](../Installing-AndroidAPS/Update-to-new-version#update-your-local-copy) (VCS->Git->Pull)
3. [Generuokite pasirašomąAPK](../Installing-AndroidAPS/Update-to-new-version#generate-signed-apk) (Pasirinkite "app", o ne "wear"!)
4. Priklausomai nuo jūsų [KG šaltinio](../Configuration/BG-Source.rst), įsitikinkite, kad [nustatytas gavėjas](../Configuration/xdrip#identify-receiver) xDrip arba naudoti modifikuotą Dexcom programą iš [2.4 aplanko](https://github.com/dexcomapp/dexcomapp/tree/master/2.4).

## Įdiegti git (jei neturite)

Vykdykite instrukcijas pagal [git instaliavimo puslapį](../Installing-AndroidAPS/git-install.rst).

## Atnaujinkite savo vietinę kopiją

* Versijos 2.7 duomenų saugyklos adresas pakeistas į <https://github.com/nightscout/AndroidAPS>. Jei nesate susipažinę su git, paprasčiausias būdas yra pašalinti esamą AndroidAPS katalogą ir pradėti [programos kūrimą nuo pradžių](../Installing-AndroidAPS/Building-APK.md).
* Spustelėkite: VCS -> Git -> Pull
    
    ![Android Studio - GIT - Pull](../images/AndroidStudio361_Update01.png)

* Spustelėkite Pull (nėra pasikeitimų dialogo srityje)
    
    ![Android Studio - GIT - Pull 2](../images/AndroidStudio361_Update02a.png)

* Palaukite, kol vyksta atsisiuntimas.
    
    ![Android Studio - Pull vyksta](../images/AndroidStudio361_Update03.png)

* Kai bus atlikta, Android Studio informuos, kad "visi failai yra atnaujinti".
    
    ![Visi failai atnaujinti](../images/AndroidStudio361_Update04.png)

## Generuoti pasirašytą APK (Generate signed APK)

<!--- Text is maintained in page building-apk.md --->

* Spustelėkite "Build" (Sukurti) meniu juostoje ir pasirinkite "Generate Signed Bundle / APK..." (Generuoti pasirašomą rinkinį / APK...).

![Kurti apk](../images/AndroidStudio361_27.png)

* Pasirinkite "APK" (1.) vietoje "Android App Bundle" ir spauskite "Next" (2.).

![APK vietoj rinkinio](../images/AndroidStudio361_28.png)

* Įsitikinkite, kad modulis yra nustatytas, į "app".
* Pasirinkite kelią į savo raktų saugyklą, paspausdami "Choose existing..." ("Pasirinkti esamą...").
* Įveskite savo slaptažodžius raktų saugyklai ir raktui.
* Jei pažymėtas laukelis slaptažodžio priminimui, nereikia jų įvesti iš naujo. Jei laukelis nebuvo pažymėtas paskutinio apk kūrimo metu ir negalite priminti slaptažodžių, skaitykite [trikčių skyrių](../Installing-AndroidAPS/troubleshooting_androidstudio#lost-keystore).
* Spauskite "Next".

![Raktų saugykla](../images/AndroidStudio361_Update05.png)

* Pasirinkite kūrimo variantą "fullRelease" (1.). 
* Pažymėkite langelius V1 ir V2 parašo versijoms(2.).
* Spustelėkite "Finish". (3.)

![Baigti kūrimą](../images/AndroidStudio361_32.png)

* Android Studio bus rodoma informacija "APK(s) generated successfully..."(APK(s) sukurtas sėkmingai...), kai kūrimas bus baigtas.
* Jei kūrimas nebuvo sėkmingas, skaitykite [trikčių diagnostikos skiltį](../Installing-AndroidAPS/troubleshooting_androidstudio.rst).
* Lengviausias būdas surasti sukurtą APK, spustelėkite ant "Event log" (įvykių žurnalai).

![Kūrimas sėkmingas - įvykių žurnalas](../images/AndroidStudio361_33.png)

* Įvykių žurnalo skiltyje spauskite "locate" (surasti).

![Įvykių žurnalas - raskite apk](../images/AndroidStudio361_34.png)

* failo, kurio ieškote, pavadinimas yra app-full-release.apk.

![APK failo vieta](../images/AndroidStudio361_35.png)

## Perkelkite APK į išmanųjį telefoną

Lengviausias būdas perkelti app-full-release.apk failą į telefoną yra [USB kabeliu ar Google Disku](https://support.google.com/android/answer/9064445?hl=en). Prašome atkreipti dėmesį, kad perdavimas elektroniniu paštu gali sukelti sunkumų ir nėra tinkamiausias būdas.

Jūsų telefone jūs turite leisti diegti programas iš nežinomų šaltinių. Instrukcijas, kaip tai padaryti, galima rasti internete (pvz., [čia](https://www.expressvpn.com/de/support/vpn-setup/enable-apk-installs-android/) arba [čia](https://www.androidcentral.com/unknown-sources)).

## Patikrinkite AAPS versiją telefone

Galite patikrinti AAPS versiją telefone, paspaudę trijų taškų meniu, ekrano viršuje, dešiniajame kampe ir tada "Apie" ("About").

![Įdiegta AAPS versija](../images/Update_VersionCheck.png)

## Trikčių šalinimas

Žr. atskirą puslapį, kuriame pateiktas [Android Studio trikčių šalinimas](../Installing-AndroidAPS/troubleshooting_androidstudio.rst).