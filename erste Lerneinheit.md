<h1> Was passiert schon an einem Freitag, der 13. </h1>

Die erste Vorlesung in BAIN (Bibliotheks- und Archivinformatik) bei Felix Lohmeier fand am 13. März 2020 in Zürich statt. 
Freitag, der 13. Und tatsächlich hingen dunkle Wolken über der Schweiz, nicht wortwörtlich, denn der Tag war wettertechnisch sehr schön, der Frühling war angekommen. Aber dennoch sollte dieser Freitag in die Schweizer Geschichte eingehen. Etwa um 15:30 Uhr verkündete die Bundesrätin Simonetta Sommaruga, dass sämtliche Schulen und Universitäten bis zum 04. April geschlossen werden. Die Studierenden konnten kaum ruhig sitzen bleiben, nervös wurde über die Auswirkungen, welche die Covid-19-Pandemie mit sich gebracht hat, diskutiert. Wie soll das Studium weitergehen? Müssen nun sämtliche Vorlesungen über Video-Übertragung gehalten werden, oder fallen sie womöglich komplett aus? Nun, nichts desto trotz wurde die Vorlesung freitags bis zum Schluss durchgezogen, die Bildung sollte unter dem Lockdown nicht leiden. Deshalb ein kurzer Einblick dazu, was ich von der ersten BAIN-Vorlesung mitgenommen habe.<p>
Gestartet wurde mit einer kurzen Zusammenfassung zum Leistungsnachweis. Jeder und jede Studierende soll innert zwei Wochen nach der Lerneinheit einen Blogartikel (ca. ein bis zwei A4-Seiten) erfassen, in welchem er oder sie die Inhalte der Vorlesung Revue passieren lässt und diese mit persönlichen Gedanken und Kritiken abrundet. Dieses sogenannte Lerntagebuch soll Online gestellt werden (z.B. auf GitHub) wo es öffentlich gemacht werden kann oder privat veröffentlicht wird.<p>
Weiter ging es in der zweiten Stunde um technische Aufklärung bezüglich der verwendeten Online-Tools für die Vorlesungen. Herr Lohmeier hat ein Online-Dokument (via GWDG) erstellt, das jedem Studenten und jeder Studentin erlaubt, Bearbeitungen vorzunehmen. Diese Art der Kommunikation scheint während Zeiten des «Social Distancing» äusserst praktisch zu sein, insofern sie von den Studierenden auch aktiv genutzt wird. Natürlich ist diese Präsentationsform ganz anders, als sie andere Dozenten für gewöhnlich nutzen. Das Fehlen der klassischen PowerPoint-Folien ist definitiv eine Sache, an die man sich zuerst gewöhnen muss.<p>
Nachdem diverse Funktionen und Tools getestet wurden, konnte mit der Vorlesung gestartet werden. Der Ablaufplan sah wie folgt aus:
-	Technische Grundlagen <p>
o	Einrichtung der Arbeitsumgebung <p>
o	Grundlagen der Unix Shell <p>
o	Versionskontrolle mit Git <p>
<p><b> Einrichtung der Arbeitsumgebung </b> <br>
Das Ziel dieses Blocks war es, eine virtuelle Maschine auf einer Cloud-Plattform einzurichten (hier: Microsoft Azure). Das gewählte Betriebssystem für diese virtuelle Maschine soll Linux (Ubuntu 19.10) sein und XFCE für die graphische Oberfläche (anstatt GNOM). Die meisten Server nutzen Linux ohne eine grafische Oberfläche, da somit eine unnötige Sicherheitslücke entfällt. Microsoft Azure bietet die Möglichkeit, eine virtuelle Maschine auf ihrem Webserver (Cloud) zu installieren, der auf Stundenbasis abbezahlt wird. Somit muss nur bezahlt werden, was auch tatsächlich genutzt wird. In BAIN wird damit gerechnet, dass jeder und jede Studierende ungefähr 40 Stunden auf diesem Webserver aufwendet. <p>
Das heisst, der «virtuelle Computer» kann, wenn er gebraucht wird, per Schalter aktiviert werden, darauf das kleine Bildschirm-Symbol klicken und per RDP verbinden. Nach drei Bestätigungen öffnet sich dann auch automatisch ein Fenster zur VM. (Das Starten der VM kann einige Zeit dauern...).<br>
Die wichtigsten Programme, die wir brauchen werden, befinden sich im Menü am unteren Fensterrand und umfassen: ein Terminal, Firefox, Dateimanager und ein Texteditor.

<b>Grundlagen der Unix Shell</b><br>
Die Unix Shell wird zur Administration von Servern genutzt und kann bei Einstellungen der Software hilfreich sein. Für einen kleinen Refresh zur Nutzung der Shell, haben wir ein paar Übungen über Library Carpentry gelöst. Folgend eine Liste einiger Kommandos, die vorgekommen sind: <p>
|Kommando| Abkürzung für | Funktion|
|--------|---------------|---------|
|cd| change directory| Wechsel in ein Directory (Verzeichnis)|
|cd ..|  | Wechsel ins Verzeichnis über dem aktuellen Verzeichnis|
|cd -|  | Wechsel in vorheriges Verzeichnis|
|ls| listing | Anzeige aller Dateien im Verzeichnis|
|ls -l|  | Anzeigen der Dateien mitsamt div. Zusatzinformation|
|ls -lh|  | Anzeigen der div. Zusationformation für den Menschen lesbar|
|~ | Homeverzeichnis | Steht jeweils zu Beginn einer Zeile|
|man| manual page | Hilfe für alle möglichen Kommando-Kombinationen|
|q| quit | Exit|
|cat|  | Zeigt gesamten Inhalt einer Datei an|
|head|  | Erster Teil einer Datei ausgeben|
|head -n 20|  | Die ersten 20 Zeilen der Datei werden ausgegeben|
|less|  | Anzeige eines Screens, mit Leertaste zum nächsten Screen, mit q Ansicht verlassen|
|tail|  | Endteil einer Datei anzeigen lassen|
|pwd | print working directory | Aktuelles Verzeichnis in Form eines Paths anzeigen lassen|
|mkdir| make directory | Neues Verzeichnis erstellen|
|mv| move | Namensänderung einer Datei oder Verschieben einer Datei (mv + Dateiname + Zielverzeichnis resp. neuer Name)|
|history|  | Liste der vergangenen gebrauchten Befehle (mit history.txt als Datei abspeichern|
|echo|  | Print des Textes, z.B. echo "Was ist los" --> Ausgabe: Was ist los|
|cp| copy | cp + Name der Kopie|
|wget| + URL | Dateien herunterladen|
|unzip| + Dateiname -d neuerDateiname | Um Datei zu entzippen, z.B. unzip shell-lesson.zip -d shell-lesson|
|rm| remove | Datei löschen|
|wc| word count | Zählung der Wörter|
|wc -l|  | Zählung der Zeilen|
|wc -l *.txt|  | Zeilenzählung in allen Dateien, die mit .txt enden|
|wc -l *.txt > lenghts.txt|  | Speichert die Ergebnisse der wc -l in einer neuen Datei, namens lengths.txt|
|wc -l *.txt \| sort -n \| head -n 1|  | Sort = Sortieren von klein nach gross, Head = nur erste Reihe wird angezeigt. Das heisst, die Zeilenzählung in den .txt Dateien wird der Grösse nach sortiert und anschliessend wird nur die erste Zeile ausgegeben|
-	Die wc-Kommandos sind Beispiele für Redirects und Pipes (|)<p>
o	Die Pipes werden genutzt, um nach einem Kommando direkt mit dem nächsten Kommando weiterzuarbeiten.<p>
o	Redirects sind wie hier wc -l *.txt > lengths.txt Funktionen, welche die Ergebnisse eines Kommandos direkt in eine Datei umlenken können.<p>
-	Die wichtigsten Kommandos sind auch [hier](https://librarycarpentry.org/lc-shell/reference.html) zu finden.<p>
<p><b>Versionskontrolle mit Git</b><br>
Git ist eine Software, die das Bearbeiten von Dateien von einer oder mehreren Personen gleichzeitig ermöglicht (d.h. ähnlich wie Google Docs oder OneDrive). Mit GitHub kann ein Git-Repository online abgelegt und anderen Nutzern zur Verfügung gestellt werden (so ist GitHub auch für das Lerntagebuch geeignet). <p>

<b>Github auf die Shell bringen</b><br>
1.	cd (um ins Heimverzeichnis zu kommen)
2.	git pull + URL ([Beispiel](https://github.com/felixlohmeier/bibliotheks-und-archivinformatik))
3.	cd bibliotheks- und archivinformatik
4.	nano 01_technische-grundlagen.md (Um Änderungen in der Datei vorzunehmen)
5.	STRG+X
6.	y (Yes für Datei speichern und verlassen)
7.	git diff (die neuen Änderungen anzeigen lassen)
8.	git status (Zeigt den aktuellen Branch an, der bearbeitet wird/wurde, resp. ob der bearbeitete Branch mit dem Master-Branch übereinstimmt oder ob Änderungen vorgenommen wurden, die nicht in den Master-Branch übertragen wurden).
9.	git add 01_technische-grundlagen.md
git status
10.	git config user.email «thommen.rachel@stud.fhgr.ch » <br>
config user.name « Rachel Thommen »
--> Damit Dateien geändert werden können, braucht das Git Repository eine Authentifizierung (E-Mail-Adresse). Wer keine Schreibrechte hat, kann auch eine Kopie der Originaldatei machen, diese bearbeiten und dem Urheber der Originaldatei per «Pull Request» zukommen lassen. Der/die Empfänger*in muss darauf bestätigen ob er oder sie die Änderung zulassen möchte oder nicht.
11.	git status <br>
git push (um das Paket, das bearbeitet wurde, über Push Request zu versenden)
