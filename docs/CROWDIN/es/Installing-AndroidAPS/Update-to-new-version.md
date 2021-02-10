# Actualizar a una nueva versión o rama

## Construyela tú mismo en lugar de descargarla

**AndroidAPS no está disponible como descarga debido a la regulación de los dispositivos mediales. ¡Es legal construir la aplicación para su propio uso, pero no debe dar una copia a los demás! Consulte la página [FAQ](../Getting-Started/FAQ.md) para obtener detalles.**

## Notas importantes

* Please update as soon as possible after a new release is available. You will receive an [information on the AndroidAPS home screen](../Installing-AndroidAPS/Releasenotes#release-notes) about the new version.
* A partir de la versión 2.3, debe utilizar git para actualizar. La actualización a través del archivo zip ya no funciona.
* As of version 2.7 repository location changed to <https://github.com/nightscout/AndroidAPS>. If you are not familiar with git the easiest way for update is remove directory with AndroidAPS and do a [new clone](../Installing-AndroidAPS/Building-APK.md).
* Utilice [Android Studio Versión 4.1.1](https://developer.android.com/studio/) o más reciente para crear el apk.
* [Windows 10 sistemas de 32 bits](../Installing-AndroidAPS/troubleshooting_androidstudio#unable-to-start-daemon-process) no son compatibles con Android Studio 4.1.1.
* Si está utilizando xDrip, asegúrese de que [identifique el receptor](../Configuration/xdrip#identify-receiver).
* Si utiliza Dexcom G6 con el [parcheado de la aplicación Dexcom](../Hardware/DexcomG6#if-using-g6-with-patched-dexcom-app) necesitará la versión de la carpeta [carpeta 2.4](https://github.com/dexcomapp/dexcomapp/tree/master/2.4).

## Rápido acceso a los usuarios experimentados

Por favor, salte este párrafo si actualiza por primera vez. El acceso rápido es para usuarios experimentados. El siguiente paso sería [instalar git](../Installing-AndroidAPS/git-install.rst) si no lo tiene ya.

Si ya ha actualizado AAPS en las versiones anteriores y utiliza un PC Windows, puede actualizar en cuatro simples pasos:

1. [Export your settings](../Usage/ExportImportSettings#export-settings) from the existing AAPS version on your phone to be on the save side
2. [Update local copy](../Installing-AndroidAPS/Update-to-new-version#update-your-local-copy) (VCS->Git->Pull)
3. [Genera APK firmado](../Installing-AndroidAPS/Update-to-new-version#generate-signed-apk) (¡selecciona 'app' en vez de 'reloj' en tu camino!)
4. Dependiendo de su [BG source](../Configuration/BG-Source.rst), asegúrese de que [identifique el receptor](../Configuration/xdrip#identify-receiver) en xDrip o utilice la aplicación Dexcom parchada de la carpeta [carpeta 2.4](https://github.com/dexcomapp/dexcomapp/tree/master/2.4).

## Instalar git (si no lo tienes ya)

Siga el manual en [git página de instalación](../Installing-AndroidAPS/git-install.rst).

## Actualice su copia local

* As of version 2.7 repository location changed to <https://github.com/nightscout/AndroidAPS>. If you are not familiar with git the easiest way for update is remove directory with AndroidAPS and do a [new clone](../Installing-AndroidAPS/Building-APK.md).
* Pulse: VCS-> Git-> Pull
    
    ![Android Studio - GIT - Pull](../images/AndroidStudio361_Update01.png)

* Pulse en Pull (sin cambios en el campo de diálogo)
    
    ![Android Studio - GIT - Pull 2](../images/AndroidStudio361_Update02a.png)

* Wait while download is in progress.
    
    ![Android Studio - Pull in progress](../images/AndroidStudio361_Update03.png)

* When done Android Studio will inform you that "all files are up-to-date".
    
    ![Todos los archivos están actualizados](../images/AndroidStudio361_Update04.png)

## Generar APK firmado

<!--- Text is maintained in page building-apk.md --->

* Click "Build" in the menu bar and select "Generate Signed Bundle / APK...".

![Crear apk](../images/AndroidStudio361_27.png)

* Seleccione "APK" (1.) en lugar de "Android App Bundle" y haga clic en "Next" (2.).

![APK instead of bundle](../images/AndroidStudio361_28.png)

* Make sure that module is set to "app".
* Select your key store path by clicking on "Choose existing...".
* Enter your passwords for key store and key.
* If the box to remember passwords is checked you don't have to enter them. In case the box was not checked during last build and you cannot remember the passwords refer to the [troubleshooting section](../Installing-AndroidAPS/troubleshooting_androidstudio#lost-keystore).
* Haga clic en "Siguiente".

![Almacén de claves](../images/AndroidStudio361_Update05.png)

* Seleccione la variante de compilación "fullRelease" (1.). 
* Marque las casillas V1 y V2 para las versiones de firma (2.).
* Haga clic en "Finalizar". (3.)

![Finalizar construcción](../images/AndroidStudio361_32.png)

* Android Studio mostrará la información "APK(s) generados con éxito..." una vez finalizada la compilación.
* En caso de que la compilación no fuera exitosa, consulte la sección [solución de problemas](../Installing-AndroidAPS/troubleshooting_androidstudio.rst).
* Easiest way to find the apk is to click on "Event log".

![Build successfully - event log](../images/AndroidStudio361_33.png)

* In the event log section click "locate".

![Event log - locate apk](../images/AndroidStudio361_34.png)

* app-full-release.apk is the file you are looking for.

![File location apk](../images/AndroidStudio361_35.png)

## Transferir APK a smartphone

Easiest way to transfer app-full-release.apk to your phone is via [USB cable or Google Drive](https://support.google.com/android/answer/9064445?hl=en). Please note that transfer by mail might cause difficulties and is not the preferred way.

On your phone you have to allow installation from unknown sources. Manuals how to do this can be found on the internet (i.e. [here](https://www.expressvpn.com/de/support/vpn-setup/enable-apk-installs-android/) or [here](https://www.androidcentral.com/unknown-sources)).

## Comprobar la versión de AAPS en el teléfono

Puede comprobar la versión de AAPS en su teléfono haciendo clic en el menú de tres puntos en la parte superior derecha y luego acerca.

![Versión de AAPS instalada](../images/Update_VersionCheck.png)

## Solución de problemas

Consulte la página separada [para la resolución de problemas de Android Studio](../Installing-AndroidAPS/troubleshooting_androidstudio.rst).