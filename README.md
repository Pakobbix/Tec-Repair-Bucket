# Tec-Repair-Bucket

WWiU Steht für Windows with integrated Updates.<br>
Dieses Skript ist aus neugierde und aus dem Mangel an Automatismus unserer Firma entstanden.
Selbst unsere NAS-Server Lösung ist eher träge und erfordert zu oft einschreiten seitens der Techniker.
Sofern der NAS nicht sowieso schon ausgeschaltet wurde, weil er das Intranet verlangsamt.

Das Skript soll abhilfe schaffen.

# Was genau macht das Skript?

Das Skript Verbindet verschiedene Tools um am ende eine Windows 10 Iso zu erstellen, die alle updates beinhaltet.
Man kann entweder direkt ein USB-Stick damit bespielen, oder die ISO einfach auf die Zielcomputer kopieren und von da aus bereitstellen.
Anders als bei WSUSoffline muss nicht erst das Funktionsupdate gemacht werden, dann WSUS Client gestartet werden und dann hoffen,
dass man kein TempAdmin Account vorfindet.
Außer natürlich bei Windows S Mode Geräte. Da geht WSUS sowieso nicht.

Bei der Erstellten Windows ISO muss nichts weiter getan werden, als das Setup.exe ausgeführt werden. Das Setup führt automatisch das Funktions-Update aus,
und installiert anschließend ohne fremde Einwirkung die Windows Kumulativen Updates.
Im Moment funktioniert das Skript soweit schonmal. 

# Was bereits enthalten ist:

Das Skript arbeitet schon selbstständig. Die Installation und automatische Aktualisierung wird von SCOOP übernommen. Dies ist eine Paketverwaltung für Windows.

Das Skript, dass einmalig von den Technikern ausgeführt werden muss, installiert scoop (Für die generelle Paketverwaltung) dann über scoop git (da die Repositories/Buckets über Github Projekte verwaltet werden.=
dann noch 7z und nircmd (Für die Aufgabenplanung. Dadurch ist es möglich, WWiU auszuführen, ohne dass die Techniker etwas davon mitbekommen, also im Hintergrund.).
Erst dann wird die Githubseite als bucket hinzugefügt und WWiU aus diesem Bucket installiert.
Das letzte was passiert ist, dass 2 Aufgaben geplant werden. 
1. WWiU alle 2 Stunden mit den höchsten Previlegien ausführen.
2. Alle 2 Stunden nach einem Update von 7z/git/nircmd und WWiU suchen.
Dadurch wird sichergestellt, dass alle 2 Wochen die neuste Windows version mit allen updates bei euch auf dem Desktop ist und das immer die neuste version des Tools vorhanden ist, ohne manuelles eingreifen.

Geplant ist noch:

Das einfügen einer Setup.exe mit Parametern (/auto upgrade /dynamicupdate disable) in die ISO. Damit auch das Automatisch abläuft.

Changelog für Leute, die noch die alte Version kannten:

1. Langsame InVoke-WebRequest durch StartBitsTransfer befehle getauscht, dadurch ca. 10fache Download Geschwindigkeit.

2. Windows 10 Downloadlink-Abfrage wieder rausgenommen, da diese nun auf einem FTP hochgeladen wurde.

3. Skript aufegräumt und alle StopLoop failsafe Funktionen rausgenommen, da diese schon in StartBitsTransfer enthalten sind.

4. Toolkit umschreibung ein wenig erweitert um Workstation/Education Index-Dateien aus der ISO zu entfernen um die ISO zu verkleinern

