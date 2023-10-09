# C# Übung - NLog via NuGet integrieren und verwenden

**Übungsfokus:** VisualStudio verwenden, NuGet-Pakete suchen, NLog verwenden

In dieser Übung geht es darum, dass du

 - Eine Konsolenanwendung in VisualStudio erstellst
 - Dir auf [NuGet](https://www.nuget.org) eine Bibliothek suchst die dir beim Logging hilft (z.B. NLog)
 - Schaue dir mindestens 2-3 der Pakete an und bekomme so ein Gefühl dafür was die enthaltenen Bibliotheken anbieten und welche Unterschiede es gibt. Dabei solltest du ruhig für jedes Paket einmal auf die Projektseite gehen und auch dort suchen ob du schnell erste Beispiele und Dokumentation findest.
 - Wähle dir nun eine Bibliothek die dir gefällt und die du einmal ausprobieren möchtest. Installiere diese in deine Anwendung.
 - In der Dokumentation der Bibliothek suchst wie du ein einfaches Beispiel erstellst (z.B. das schreiben einer Log-Nachricht in eine Log-Datei)
 - Das Beispiel in deiner Anwendung umsetzt

Mit dieser Übung trainierst einerseits die praktische Verwendung der für dich wichtigen Tools (VisualStudio und NuGet) und übst wie du dich in eine neue Bibliothek einarbeitest.

## Erweiterung der Übung für Fortgeschrittene

Eine sehr gute Ergänzung dieser Übung ist die Verwendung von Git. Stelle also nach jedem Schritt sicher, dass deine Anwendung gestartet werden kann (auch wenn sie nichts macht. Wichtig ist nur, dass es keine Fehler/Warnungen vom Kompiler gibt) und mache dann einen Commit. 

ZUSATZ: Erstelle nicht nur einfach einen Commit, sondern überlege/recherchiere explizit wie eine gut Commit-Message aussieht und formuliere eine entsprechende Message für jeden Commit.

Mit dieser Ergänzung stellst du sicher, dass du in deiner Entwicklungsumgebung die Versionskontrolle bedienen kannst und das du alle wichtigen Informationen in eine Commit-Message bringst.

## Artikel, Videos & Links zu dieser Aufgabe

Wenn dir noch gar nicht klar ist wofür du [NuGet](https://www.nuget.org) überhaupt verwenden kannst, dann solltest du dir das Video [C# Tutorial Deutsch - Warum NuGet](https://youtu.be/WsvhwW2M7AY) anschauen.

Es gibt einige gute Artikel zum Thema was sollte in eine Commit-Message. [Dieser Artikel](https://stories.devacademy.la/how-to-use-github-like-a-proper-human-being-1a9c895c4e13#.hk1ywo6hi) gehört dazu. Er geht jedoch noch weiter und zeigt dir welche anderen Teile eines GitHub-Projektes du anpassen solltest, wenn dir professionelles Arbeiten wichtig ist. 

## Lösung

Hast du die Aufgabe umgesetzt, oder willst du nur ein wenig spicken? Mach es dir nicht zu einfach ;-). Du willst schließlich was lernen, oder?

Führe fogende Schritte aus, wenn du keine Idee hast, wie du die Übung angehen kannst:

 - [ ] Erstelle eine Konsolenanwendung ([hier eine leere](https://github.com/LernMoment/csharp-uebungen/tree/7c7710bcc18ba4ee41ca96495a858e3c3e5737bb/BibliothekenIntegrieren-NLog))
 - [ ] Suche auf [nuget.org](https://www.nuget.org) mit dem Stichwort `Log` nach Paketen die dich beim Logging unterstützen.
 - [ ] Für mich ist zum Beispiel der 2. Eintrag [NLog](https://www.nuget.org/packages/NLog) ansprechend. Dieses habe ich mir genauer angeschaut. (Ich habe beispielsweise [log4net](https://www.nuget.org/packages/log4net/) übersprungen, weil ich relevante Informationen auf der [Project Site](http://logging.apache.org/log4net/) nicht direkt finden konnte)
  - [ ] Über den Link *Project Site* von der [NLog Beschreibungsseite](https://www.nuget.org/packages/NLog) bin ich auf die [NLog-Seite](http://nlog-project.org) gekommen und fand es recht ansprechend.
  - [ ] Von der NLog-Projektseite bin ich zum [GitHub-Verzeichnis](https://github.com/NLog/NLog/) gekommen und habe dort auch das [Tutorial](https://github.com/NLog/NLog/wiki/Tutorial) gefunden.
  - [ ] Aus dem [Tutorial](https://github.com/NLog/NLog/wiki/Tutorial) konnte ich sehen wie ich eine Einfache Anwendung mit Logging erstelle und habe mich für diese Bibliothek entschieden.
 - [ ] Zur Installation von NLog gehst du im *Projektmappenexplorer* auf deine *Projektmappe* und wählst aus dem Kontextmenü *"NuGet Pakete für Projektmappe verwalten ..."* aus
  - [ ] Im sich öffnenden Dialog wählst du oben links *"Durchsuchen"* aus und suchst dann nach NLog. Bei mir ist das der erste Eintrag.
  - [ ] Sobald du das passende Paket ausgewählt hast, kannst du im mittleren Teil deines Fenster auswählen (Checkbox) für welches Projekt in deiner Projektmappe du NLog installieren möchtest. Hier wählst du entweder alle Projekte aus, oder nur die in denen du NLog benötigst. Da ich nur ein Projekt in meiner Projektmappe habe was das einfach ;).
  - [ ] Nun kannst du bei *"Version"* noch eine andere Version auswählen. Bei mir war die *"Aktuelleste Vorabversion"* ausgewählt. Diese habe ich getauscht gegen die *"Aktuelleste stabile Version"* und dann *"Installieren"* ausgewählt.
 - [ ] Nach der Installation hast du sowohl eine neue `packages.config` in deinem Projekt wie auch einen neuen Verweis auf NLog. In [diesem Commit](https://github.com/LernMoment/csharp-uebungen/commit/f8004190399e8a4956bbd33ffb0da19258ae45fc) siehst du was sich in meinem Projekt geändert hat.
 - [ ] Nun kannst du mit Hilfe des [Tutorials einen `Logger` anlegen](https://github.com/NLog/NLog/wiki/Tutorial#creating-loggers). Dazu brauchst du lediglich die Zeile `private static Logger logger = LogManager.GetCurrentClassLogger();` in deine Klasse `Program` schreiben und per `using` einen entsprechenden `Namespace` einbinden. Hier [mein Commit](https://github.com/LernMoment/csharp-uebungen/commit/2618dc4ea9c31c3111b044f1a73c1317df651c1f) dazu.
 - [ ] Der `Logger` alleine macht jedoch noch nichts. Daher zeigt das [Tutorial im Abschnitt Log-Messages](https://github.com/NLog/NLog/wiki/Tutorial#writing-log-messages) wie du eine Message in das Log schreiben kannst. Hier mein passendes [Commit](https://github.com/LernMoment/csharp-uebungen/commit/5c0f234192ea06c2d47ba0757cc6c3988517761d).
 - [ ] Auch jetzt wird allerdings noch immer kein Logfile erzeugt. Das liegt daran, dass NLog [eine Konfiguration benötigt](https://github.com/NLog/NLog/wiki/Tutorial#configuration). Dies ist jedoch schlecht im Tutorial beschrieben. Erstelle also eine Datei `NLog.config` über *"Hinzufügen -> Neues Element ..."* an deinem Projekt und nenne sie `NLog.config`. Bei mir sieht das [so aus](https://github.com/LernMoment/csharp-uebungen/commit/20b6c3423c608bef4e9d68448127ebfb8651c6b6).
 - [ ] Nun wird es verwirrend, weil trotz der Datei kein Logfile erzeugt wird beim Starten der Anwendung. Dies liegt daran, dass die Datei `NLog.config` im Ausgabeverzeichnis benötigt wird, während die Anwendung ausgeführt wird. Wähle also im *Projektmappenexplorer* die Datei `NLog.config` aus und in den Eigenschaften stellst du den Eintrag *"In Ausgabeverzeichnis kopieren"* von `Nicht kopieren` auf `Immer kopieren`.

