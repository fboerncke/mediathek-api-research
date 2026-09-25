# Hörfassungen finden

**Barrierefreie Fassungen in den öffentlich-rechtlichen Mediatheken: produziert, bezahlt – und kaum auffindbar.**

ARD, ZDF und ARTE produzieren Sendungen mit Hörfassung (Audiodeskription), in
Gebärdensprache, in Einfacher Sprache und mit Klarer Sprache. Bezahlt werden sie aus dem
Rundfunkbeitrag, gemacht werden sie für Menschen, die sie brauchen: blinde und
sehbehinderte Menschen, gehörlose und schwerhörige Menschen, Menschen, die auf
vereinfachte Sprache angewiesen sind.

Wer eine solche Fassung sucht, stößt auf ein Problem, das auf den ersten Blick
klein wirkt und auf den zweiten erstaunlich tief ist: **Es gibt keine offene,
dokumentierte Schnittstelle, die für eine Sendung verlässlich sagt, welche barrierefreien
Fassungen es von ihr gibt.** Jeder Sender beschreibt sie anders, jedes Programm, das
Mediatheken senderübergreifend durchsucht, rät auf seine Weise, und der Mensch am Ende
der Kette findet – oder eben nicht.

Dieses Repository dokumentiert das Problem. Die Analyse beruht auf einer eigenen
Messung: rund 594.000 Einträge aus den Mediatheken und rund 2.200 einzelne Nachfragen bei
den Sendern, Stand 25.09.2026. Die Beispiele sind verlinkt, damit sich jeder selbst ein
Bild machen kann. Mediatheken nehmen Sendungen nach Ablauf der Rechte wieder heraus;
ein Link kann deshalb irgendwann ins Leere führen.

---

## Warum das kein Randthema ist

Der Medienstaatsvertrag bestimmt, was ein barrierefreies Angebot ist: eines, das für
Menschen mit Behinderungen **auffindbar**, zugänglich und nutzbar ist – in dieser
Reihenfolge (§ 2 Abs. 2 Nr. 30 MStV). Die Sender haben in den vergangenen Jahren viel
produziert: Allein vom Tatort gibt es in den Mediatheken derzeit fast 400 Folgen mit
Hörfassung.

Aber eine Fassung, die niemand findet, hilft niemandem. Und hier liegt die eigentliche
Asymmetrie: Wenn ein technisches Format bricht, merkt es sofort jemand, und es gibt eine
Fehlermeldung. Wenn eine Hörfassung unauffindbar bleibt, merkt es niemand. Die
betroffenen Personen haben keine laute Stimme, sind über das ganze Land verteilt, und 
ihre erfolglose Suche erzeugt keinen Fehlerbericht.

Selbst für Menschen, die uneingeschränkt sehen können, ist die Suche in den Mediatheken 
schon mühsam. Jeder Sender bietet eine eigene Mediathek an, und jede funktioniert ein wenig 
anders. Für Menschen, die auf Hörfassungen angewiesen sind und mit Screenreader oder per 
Sprache suchen, ist es deutlich komplizierter. Hier entscheidet die Datenqualität wesentlich 
darüber, ob eine Hörfassung gefunden wird oder unsichtbar bleibt.

---

## Das Problem in seiner Vielfalt

Die naheliegende Annahme lautet: „Man muss doch nur nachsehen, ob ‚Hörfassung‘ dabeisteht.“
Die folgenden Abschnitte zeigen, warum das nicht reicht. Jeder Fall stammt aus echten Daten.

### 1. Es gibt nicht *die* Hörfassung

Dieselbe Sache kommt in ganz verschiedenen Formen daher:

| Form | Beispiel |
|---|---|
| eigene Datei auf derselben Seite | Tatort „[Donuts](https://www.ardmediathek.de/video/Y3JpZDovL2Rhc2Vyc3RlLmRlL3RhdG9ydC8yMDIzLTA0LTAyXzIwLTE1LU1FU1o)“ (ARD): Normale Fassung und Hörfassung sind zwei Videodateien unter einer Adresse. Die Datei mit der Hörfassung heißt ausgerechnet „internationalerton“. |
| eigener Beitrag mit eigener Adresse | Tatort „Unter Feuer“ (MDR): [normale Fassung](https://www.ardmediathek.de/video/Y3JpZDovL21kci5kZS9zZW5kdW5nLzI4MjA0MC81MTQ0NzgtNDk0NDk5) und [Hörfassung](https://www.ardmediathek.de/video/Y3JpZDovL21kci5kZS9zZW5kdW5nLzI4MjA0MC81MTQ0NzgtNDk0NDk5L2F1ZGlvZGVza3JpcHRpb24) sind zwei getrennte Seiten. |
| umschaltbare Tonspur – und zusätzlich eigener Beitrag | Tatort „Licht“ (HR): Auf der [normalen Seite](https://www.ardmediathek.de/video/MzlkYWUyNGQtYTliMi00ZTVkLTg5MzMtMWU3NTk4ZDJlYzYz) meldet die ARD-Mediathek eine Hörfassung als Tonspur im Player; daneben gibt es sie als [eigenen Beitrag](https://www.ardmediathek.de/video/MzlkYWUyNGQtYTliMi00ZTVkLTg5MzMtMWU3NTk4ZDJlYzYzL2F1ZGlvZGVza3JpcHRpb24). |
| nur in einer anderen Sprache | „[Das U-Boot (1/2)](https://www.arte.tv/de/videos/095101-001-A/das-u-boot-1-2/)“ (ARTE): Auf der deutschen Seite gibt es die Hörfassung nur auf Französisch. |

### 2. Ein Name, zwei völlig verschiedene Dinge

„Klare Sprache“ und „Einfache Sprache“ klingen fast gleich und haben nichts miteinander zu tun:

- **Einfache Sprache / Leichte Sprache** verändert den **Text**: kürzere Sätze,
  einfachere Wörter. Beispiel: die tägliche „tagesschau in Einfacher Sprache“.
- **Klare Sprache** verändert den **Ton**: Musik und Geräusche leiser, Dialog lauter,
  die Wörter bleiben gleich. Sie hilft Menschen, die schlecht hören.

Der europäische Rundfunkstandard DVB trennt beide ausdrücklich. In den Mediatheken tritt
Klare Sprache in zwei Gestalten auf: beim WDR als eigene Datei mit „(klare Sprache)“ im
Titel, etwa beim Tatort „[Die letzten Menschen von Köln](https://www.ardmediathek.de/video/Y3JpZDovL3dkci5kZS9CZWl0cmFnLXNvcGhvcmEtYjM2NzBlNDMtOTBmMC00YTQxLWE5M2QtNTlhYWU3NGI0N2Ew)“,
und in der ARD-Mediathek als Tonspur im Player, etwa bei „[Haus der Toten – Tod am Rennsteig](https://www.ardmediathek.de/video/Y3JpZDovL2FyZC5kZS9wbGFuQVJEX2E2MjNhM2FmLTA2MTctNDA3Mi1hODFiLWZiZjVhMjE5NGVlM19nYW56ZVNlbmR1bmc)“.
Diese Tonspur wird in keinem einzigen Titel erwähnt. Eine Suche nach dem Wort findet also
nur einen Teil, und eine Suche, die beide Begriffe zusammenwirft, schickt einen
schwerhörigen Menschen zu Nachrichten in vereinfachter Sprache.

### 3. Jeder Sender spricht seine eigene Sprache

Die Sender *haben* die Merkmale strukturiert. Nur eben jeder anders, und keiner über eine
offene, dokumentierte Schnittstelle:

| | ARD | ZDF | ARTE |
|---|---|---|---|
| Zugang | interne Schnittstelle der Mediathek | Angaben stecken in der Videoseite; eine dokumentierte Schnittstelle gibt es, aber nur auf Antrag | Konfiguration des Players |
| Hörfassung, Untertitel, Gebärdensprache | eine Liste: `["UT","AD","DGS"]` | drei Felder, deren bloßes *Vorhandensein* „ja“ bedeutet | je Sprachfassung: `audioDescription`, `closedCaptioning` |
| Ablaufdatum | `availableTo` | `visibleTo` | `rights.end` |
| Sprachcode | `deu`, `fra` | – | `de`, `fr` |

Dazu kommen Eigenheiten, die man erst findet, wenn man hinsieht:

- An 16 Adressen meldet die ARD-Mediathek statt einer Sprache nur „ov“, etwa bei der
  Serie „[Soul Shift](https://www.ardmediathek.de/video/MDU1NjQyNGEtNGU4ZS00MTg4LTllNWMtNzFiZWE0NjNlNTgy)“.
- ARTE benennt dieselbe Fassung je nach Sprache der Abfrage anders: „OmU-POL“ in der
  deutschen, „POL“ in der polnischen Antwort.
- Gebärdensprache steht in den Titeln als „(Gebärdensprache)“, „(mit Gebärdensprache)“,
  „(Mit Gebärdensprache)“ oder „(DGS)“. Im Datenfeld der ARD-Mediathek heißt sie `DGS`.

Auch diese Aufstellung mag unvollständig sein, weil sie auf der Basis von eigener Analyse erhoben wurde und nicht auf der Basis von Dokumentation.

### 4. Das Wort im Titel ist kein Datenfeld

Programme, die mehrere Mediatheken zugleich durchsuchen, bekommen die Merkmale meist nur
als Wort im Titel. Das hat drei Folgen:

- **Wer das Wort schreibt, ist nicht immer der Sender.** In der ARD-Mediathek heißt die
  Folge schlicht „Donuts“. Erst auf dem Weg in die senderübergreifende Liste wird daraus
  „Donuts (Audiodeskription)“.
- **Ein Wort kann täuschen.** „[In der Tonkabine: So entstehen Hörfilme](https://www.ardmediathek.de/video/Y3JpZDovL21kci5kZS9iZWl0cmFnL2Ntcy9lNTcwOTAzMS00MWI1LTQ4OGEtYmFjYy04ZWM4NzEyMjhhMzI)“
  ist ein Beitrag über Hörfilme, aber selbst keiner. „[Leichte Sprache braucht fast jeder zehnte Mensch](https://www.ardmediathek.de/video/Y3JpZDovL3N3ci5kZS9hZXgvbzIwNzc3MjE)“
  ist ein Beitrag *über* Leichte Sprache, nicht *in* ihr. Ein verbreitetes Programm wertet
  schon „AD |“ oder „Hörspiel“ im Titel als Hinweis auf eine Hörfassung – und kündigt so
  „Das Ende von THE WALKING DE**AD** | TOP 5“ oder „Die Pfefferkörner gibt's auch als
  **Hörspiel**!“ als Hörfassung an. Das betrifft 48 Einträge in der untersuchten Stichprobe,
  keiner davon ist eine.
- **Ein fehlendes Wort ist kein Nein.** Steht nichts im Titel, weiß man nur, dass nichts
  dasteht. Ob es eine Hörfassung gibt, sagt allein der Sender.

### 5. Was zählt man überhaupt? Wie misst man korrekt?

Eine Tatort-Folge kann in der Liste dreimal vorkommen: normal, mit Hörfassung, in
Gebärdensprache. Für einen Menschen ist das **eine Sendung** in drei **Fassungen**.

Wer das nicht auseinanderhält, misst Unsinn. Beim Tatort stehen 1.416 Einträge für 918
Sendungen. Die eigene Messung dieses Vorhabens ist genau daran mehrfach gescheitert: Eine
erste Auswertung ergab, dass bei 12 % der Sendungen mit Hörfassung der Hinweis fehlt.
Übrig blieb nach sechs Korrekturen **keine einzige** Sendung, deren deutsche Hörfassung in
der Liste ganz fehlt. Jede Korrektur war eine bis dahin unbekannte Schreibweise, die
dieselbe Sendung wie zwei verschiedene aussehen ließ: „(mit Untertitel)“,
„(Originalversion …)“, „(Englisch)“ – und zuletzt dies: Dieselbe Folge der „Rentnercops“
steht unter derselben Adresse einmal als
„[Folge 3: Altes Eisen](https://www.ardmediathek.de/video/Y3JpZDovL3dkci5kZS9CZWl0cmFnLTNlZjMwNjE2LTI0MDQtNGU1NS05NWZlLTZlMjZhYzJjODM5Ng)“
(Sender ARD) und einmal als „Folge 43: Altes Eisen“ (Sender WDR). Die Hörfassung gibt es
nur beim zweiten Eintrag.

Die Lehre daraus: Wer Einträge zählt statt Sendungen,
findet Probleme, die es nicht gibt, oder übersieht die, die es gibt.

### 6. Sprache ist ein eigenes Merkmal

Eine Hörfassung auf Französisch hilft einem deutschsprachigen blinden Menschen nicht.
Bei ARTE gibt es Sendungen, deren Hörfassung nur in einer Sprache vorliegt. In der eigenen
Stichprobe sind es 18. Das ist kein Fehler irgendeiner Liste, sondern ein Angebot, das so
gemacht ist. Es muss aber als solches erkennbar sein, sonst verspricht eine Suche eine
Fassung, die man nicht verstehen kann.

### 7. Die Zeit läuft

Sendungen verschwinden wieder aus den Mediatheken, manche nach Tagen, manche nach Jahren.
Wer eine Hörfassung sucht, will wissen, ob sie morgen noch da ist. Die Sender kennen das
Ablaufdatum: Für 1.810 der 2.248 befragten Adressen nennen sie eines in der Stichprobe.
Die verbreitete senderübergreifende Liste hat dafür kein Feld.

### 8. Ja, nein – und ungeprüft

Aus alldem folgt die wichtigste Unterscheidung: Ein barrierefreies Merkmal hat **drei**
Zustände, nicht zwei.

- **ja** – der Sender bestätigt es, oder es gibt die Datei
- **nein** – der Sender wurde gefragt und verneint
- **ungeprüft** – niemand hat gefragt, es wurde noch nicht gemessen

Die meisten Suchen kennen nur „gefunden“ und „nicht gefunden“ und machen damit aus jedem
„ungeprüft“ stillschweigend ein „nein“. Eine ehrliche Antwort auf „Welche Krimis gibt es mit
Hörfassung?“ lautet deshalb: „Diese hier, und bei so und so vielen weiteren ist es noch
nicht geprüft.“

---

## Zwei Ursprünge, zwei Adressaten

Nicht jedes Problem hat dieselbe Ursache, und nicht jedes lässt sich an derselben Stelle
lösen. Diese Analyse trennt deshalb strikt:

| Ursprung | Beispiele | Wer könnte es lösen |
|---|---|---|
| **an der Quelle, beim Sender** | verschiedene Formen der Hörfassung; unterschiedliche Feldnamen und Sprachcodes; Hörfassung nur in einer Fremdsprache; „Klare Sprache“ als verwechselbarer Name; keine offene, dokumentierte Schnittstelle | die Sender |
| **auf dem Weg zu den Programmen** | Merkmal nur als Titelwort; kein Feld für Tonspuren, Ablaufdatum oder ein geprüftes Nein; verlorene Untertitel; dieselbe Sendung unter verschiedenen Sendern, Themen oder Folgennummern | alle, die Mediathekdaten aggregieren und weitergeben |

Viele unabhängige Programme beziehen ihre Mediathekdaten aus derselben gemeinsamen Liste,
der MediathekView-Filmliste. Sie wird seit über fünfzehn Jahren ehrenamtlich gepflegt. Das
ist eine große Leistung, und diese Analyse will sie nicht ersetzen, sondern sucht nach
Wegen zur Ergänzung. Das Problem selbst liegt tiefer: Es beginnt bei den Sendern, und jedes
Programm, das Mediatheken durchsuchbar machen will, stößt darauf.

---

## Was die Messung zeigt – und was nicht

Stand 25.09.2026. Gezählt werden **Sendungen**, nicht Einträge.

- **Größe des Angebots:** rund eine halbe Million Sendungen, davon rund 330.000 mit
  mindestens fünf Minuten Länge.
- **Stichprobe:** 2.248 Adressen bei ARD, ZDF und ARTE einzeln nachgefragt. Laut Sender
  haben 465 der zugehörigen Sendungen eine Hörfassung.
- **Hörfassung in der Sprache des Kanals:** Bei 447 Sendungen. Jede davon ist in der
  verbreiteten Liste irgendwo gekennzeichnet – bei vier allerdings nur unter einem anderen
  Sender, Thema oder Folgentitel.
- **Hörfassung nur in anderer Sprache:** 18 Sendungen, ein Angebot des Senders.
- **Klare Sprache:** 80 Einträge als eigene Datei, dazu 81 Adressen, an denen sie als
  Tonspur in keinem Titel steht.
- **Einfache Sprache:** 473 Einträge, nur über das Titelwort auffindbar.

**Was das bedeutet:** Wo eine Hörfassung in der Sprache des Kanals vorliegt, wird sie in
der Stichprobe fast immer irgendwie gekennzeichnet. Die Häufigkeit der Lücke ist nicht das
Hauptproblem. Das Hauptproblem ist die Konstruktion: Eine Kennzeichnung per Titelwort kann
nicht sagen, was *geprüft* fehlt, was bald verschwindet, welche Tonspur in einer Datei
steckt und in welcher Sprache eine Fassung vorliegt.

**Was die Zahlen nicht sagen:** Die Stichprobe ist nicht repräsentativ.

- **Ein Drittel ist Tatort.** 744 der 2.248 befragten Adressen gehören zum Tatort, weil die
  Messung dort begann. Der Tatort ist eine der am besten versorgten Reihen überhaupt.
- Die Stichprobe liegt deshalb deutlich dichter an Sendungen mit Hörfassung als der
  Gesamtbestand.
- Sie deckt weniger als 1 % der abfragbaren Adressen ab und nur drei Sender. KiKA, 3sat,
  PHOENIX, SR und DW sind noch gar nicht angebunden.

---

## Es fehlt kein Standard

Man könnte meinen, es fehle an einer Vereinbarung, wie man so etwas beschreibt. Das
stimmt nicht. Es gibt zwei anerkannte Standards, für zwei Welten:

- **TV-Anytime** (ETSI TS 102 822): die europäische Norm der Rundfunkwelt. Mit ihr
  kennzeichnet der Rundfunkstandard DVB Hörfassung und Klare Sprache, auch im
  Internet-Fernsehen (DVB-I).
- **schema.org**: das gemeinsame Vokabular des Webs, das Suchmaschinen verstehen. Seine
  Merkmale zur Barrierefreiheit sind für barrierefreie E-Books bereits Pflicht (W3C,
  EPUB Accessibility 1.1).

Was fehlt, ist die Übersetzung zwischen den Welten. Die Merkmale stecken in der
Rundfunkwelt fest und kommen im Web nicht an. Und wo ein Standard schweigt, muss man das
sagen: schema.org kennt zum Beispiel keinen Wert für Klare Sprache.

---

## Was es bräuchte

Keine neue Mediathek und keine neue App, sondern eine **offene Datengrundlage**, die jedes
bestehende Programm nutzen kann:

- für jede Sendung: welche barrierefreien Fassungen es gibt, in welcher Sprache, wie
  ausgeliefert (eigene Datei oder Tonspur) und bis wann verfügbar
- mit **ja, nein und ungeprüft**, und mit der ehrlichen Angabe, wie vollständig eine
  Antwort ist
- ausgegeben in den anerkannten Standards, statt ein eigenes Format zu erfinden;
- aus öffentlich erreichbaren Quellen, **schonend** erhoben: Nachfragen beim Sender nur
  für Neues, begrenzt viele Serveranfragen pro Zeit, nie parallel
- ohne eigenen Bestand an Inhalten: keine Videos, keine Untertitel, nur Aussagen über
  Sendungen
- als freie Software zum **Selbstbetreiben**, bis hinunter auf einen Raspberry Pi. Eine 
  solche Lösung braucht keine Rechenpower sondern Datenqualität und -integrität. Denn 
  der größte Teil der Arbeit ist nicht Programmierung. Er besteht darin, jeden dieser
  Fälle an der Quelle zu identifizieren, zu prüfen und sauber einzuordnen.

---

## Wer dahintersteht

Frank Börncke, freiberuflicher Softwareentwickler. Seit Jahren betreibe ich kostenlos
„Meine Mediathek“, eine Sprachanwendung, mit der man die Mediatheken von ARD, ZDF und ARTE
per Sprache durchsuchen und abspielen kann, auch ohne Bildschirm. Im mehrjährigen Betrieb 
habe ich gelernt, wo die Grenzen der heutigen Datenlage liegen, gerade beim barrierefreien 
Zugang.

Dieses Vorhaben hat keine Gewinnabsicht. Es versteht sich als **Diskussionsbeitrag**: Es
will zeigen, dass Auffindbarkeit technisch möglich ist, und liefert Zahlen, wo bisher
niemand welche hatte. Die Einzelteile einer Lösung sind bekannt. Es muss sich nur jemand
darum kümmern.

**Kontakt und Hinweise** sind willkommen, besonders von Menschen, die Hörfassungen,
Gebärdensprache oder Klare Sprache selbst nutzen, und von Projekten, die Mediathekdaten
verarbeiten.

---

*Alle Zahlen: eigene Messung, Stand 25.09.2026. Die Mediathekdaten ändern sich täglich. 
Die Links in die Mediatheken haben zum Zeitpunkt der Veröffentlichung funktioniert.*
