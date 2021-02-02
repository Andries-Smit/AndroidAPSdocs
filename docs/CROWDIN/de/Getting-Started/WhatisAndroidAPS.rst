Was ist ein Closed Loop System mit AndroidAPS?
**************************************************

AndroidAPS ist eine App, die als künstliche Bauchspeicheldrüse (artificial pancreas system - APS) auf einem Android-Smartphone arbeitet. Was ist eine künstliche Bauchspeicheldrüse? Es ist eine App, die darauf abzielt, das zu tun, was eine funktionierende Bauchspeicheldrüse tut: den Blutzuckerspiegel automatisch in gesunden Grenzen zu halten. 

Ein APS kann die Aufgabe nicht so gut erfüllen wie eine biologische Bauchspeicheldrüse, aber es kann die Behandlung von Typ-1-Diabetes mit handelsüblichen Geräten und einer einfachen und sicheren Software erleichtern. Diese Geräte beinhalten einen kontinuierlichen Glukosemonitor (CGM), um AndroidAPS über Deinen Blutzuckerspiegel zu informieren, und eine Insulinpumpe, die von AndroidAPS gesteuert wird, um die passenden Insulindosen zu liefern. Die App kommuniziert mit diesen Geräten über Bluetooth. Es führt seine Dosisberechnungen unter Verwendung eines Algorithmus oder eines Regelsatzes durch, der für eine andere künstliches Bauchspeicheldrüse, OpenAPS genannt, entwickelt wurde. 

Ein Hinweis zur Vorsicht: AndroidAPS wird nicht von einer medizinischen Aufsichtsbehörde reguliert. Die Verwendung von AndroidAPS ist im Wesentlichen die Durchführung eines medizinischen Experiments an sich selbst. Die Einrichtung des Systems erfordert Entschlossenheit und technisches Wissen. Wenn Dir zu Beginn das technische Know-how noch fehlt, wirst Du es am Ende haben. Oder Du kannst Deine Fragen in Facebook-Gruppen oder anderen Foren an erfahrene Nutzer stellen. Viele unterschiedliche Menschen mit Diabetes haben AndroidAPS erfolgreich erstellt und nutzen es nun ganz sicher.

* das System selbst erstellt, damit er/sie vollständig versteht, wie es funktioniert.
* seine individuellen Diabetes-Einstellungen zusammen mit seinem Diabetes-Team anpasst, so dass diese bestmöglich funktionieren.
* das System pflegt, auf dem aktuellen Stand hält und es überwacht, um sicherzustellen, dass es ordnungsgemäß funktioniert.

.. note:: 
	**Disclaimer und Warnung**

	* Sämtliche Informationen, Gedanken und der Quellcode sind nur für informatorische und wissenschaftliche Zwecke. Nightscout erfüllt keinerlei Anforderungen des Datenschutzes im Gesundheitswesen. Verwenden Sie Nightscout und AndroidAPS auf eigenes Risiko und setzen Sie es nicht ein, um Behandlungsentscheidungen zu treffen.

	* Bei Nutzung des Quellcodes von github.com bestehen keinerlei Gewährleistungs- und Garantieansprüche. Please review this repository's LICENSE for details.

	* Sämtliche Produkt- und Herstellernamen, Handelsmarken, Dienstleistungsmarken, Warenzeichen und eingetragene Dienstleistungsmarken sind Eigentum ihrer jeweiligen Inhaber und werden nur zu Informationszwecken genutzt und nicht für Werbung oder Marketing. Ihre Verwendung dient nur zur Information und bedeutet weder, dass AAPS zu ihnen gehört, noch dass sie unterstützt werden.

	Bitte beachten: Dieses Projekt steht in keinerlei Verbindung mit `SOOIL <http://www.sooil.com/eng/>`_, `Dexcom <https://www.dexcom.com/>`_, `Accu-Chek, Roche Diabetes Care <https://www.accu-chek.com/>`_, `Insulet <https://www.insulet.com/>`_ oder `Medtronic <https://www.medtronic.com/>`_.
	
Wenn Du bereit bist, diese Herausforderung anzunehmen, lies bitte weiter. 

Die primären Ziele von AndroidAPS
==================================================

* Eine App mit eingebauter Sicherheit. Um mehr über die Sicherheitsfunktionen der Algorithmen, die als oref0 und oref1 bekannt sind, zu lesen, klicke hier (https://openaps.org/reference-design/)
* Eine All-in-one-App für das Management Deines Typ1-Diabetes mit einer künstlichen Bauchspeicheldrüse und Nightscout.
* Eine App, zu der Benutzer bei Bedarf Module einfach hinzufügen oder entfernen können.
* Eine App mit Versionen für verschiedenen Standorte und Sprachen.
* Eine App, die im Open- und Closed-Loop-Modus verwendet werden kann.
* Eine App, die vollkommen transparent ist: Benutzer können Parameter eingeben, Ergebnisse sehen und die endgültige Entscheidung treffen.
* Eine App, die unabhängig von bestimmten Pumpen-Treibern ist und eine "virtuelle Pumpe" enthält, damit Benutzer sicher experimentieren können, bevor sie diese zusammen mit ihrer Insulinpumpe verwenden. 
* Eine App, die eng mit Nightscout verbunden ist.
* Eine App, in der der Benutzer die Kontrolle über die Sicherheitseinschränkungen hat. 

How to start
==================================================
Of course, all of this content here is very important, but can be in the beginning quite confusing.
Gute Orientierung bieten die `Modul-Übersicht <../Module/module.html>`_ und die `Objectives (Ziele) <../Usage/Objectives.html>`_. Du kannst Dir zuerst auch einmal das `Sample Setup mit Dana, Dexcom und Sony Smartwatch <../Getting-Started/Sample-Setup.html>`_ ansehen.
 
