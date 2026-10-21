# Barrierefrei produziert – aber nicht barrierefrei zu finden

**Barrierefreie Fassungen in den öffentlich-rechtlichen Mediatheken: produziert, bezahlt und ohne verlässliche Auskunft.**

ARD, ZDF und ARTE produzieren Sendungen mit Hörfassung, in Gebärdensprache, in Einfacher Sprache und mit Klarer Sprache. Eine Hörfassung (auch Audiodeskription oder Hörfilm genannt) ist eine zusätzliche Tonspur, die beschreibt, was im Bild passiert. Bezahlt werden all diese Fassungen aus dem Rundfunkbeitrag. Gemacht werden sie für Menschen, die sie brauchen: blinde und sehbehinderte Menschen, gehörlose und schwerhörige Menschen, Menschen, die auf vereinfachte Sprache angewiesen sind.

Man sollte meinen, es genüge nachzusehen, ob „Hörfassung“ dabeisteht. Dieses Repository
zeigt an echten Beispielen, warum das nicht reicht. Die Probleme haben zwei Ursprünge,
und man muss sie auseinanderhalten:

**Erstens die Sender.** ARD, ZDF, ARTE, KiKA und PHOENIX beschreiben barrierefreie Fassungen
jeder für sich: mit eigenen Wörtern, eigenen Datenfeldern, eigenen Auslieferungsformen.
**Es gibt keine offene, dokumentierte Schnittstelle, die senderübergreifend beantwortet,
welche barrierefreien Fassungen es von einer Sendung gibt.** Das ist die Wurzel. Die Sender
haben einen gesetzlichen Auftrag zur Barrierefreiheit (dazu unten mehr), und eine gemeinsame
Auskunft als API-Schnittstelle darüber, was es gibt, wäre der naheliegende Teil davon. 

**Zweitens der Weg zu den Programmen.** Wer diese uneinheitlichen Daten an der Quelle 
einsammelt und konsolidiert weitergibt, der muss sie in ein gemeinsames Format bringen,
so gut es geht. Da die Struktur der Daten an der Quelle aber nicht umfassend dokumentiert ist,
kann es passieren, dass Information verloren geht oder verdreht wird. 

Mit dieser Situation kämpft heute in erster Reihe die **[MediathekView-Filmliste](https://mediathekview.de/)** 
(nachfolgend kurz „die Filmliste“ genannt). Sie ist das einzige Angebot, das diese Arbeit in dieser
Breite und Qualität leistet, und darum der De-facto-Standard für viele Open-Source-Projekte.
Die Uneinheitlichkeit, mit der sie kämpft, haben die Sender hinterlassen. Jedes andere
Projekt, das die Mediatheken senderübergreifend an der Quelle durchsuchbar machen wollte,
wäre genauso gezwungen, auf seine Weise zu raten und zu interpretieren. 

Das ehrenamtliche Projekt MediathekView trägt in der Liste seit gut 18 Jahren mehrmals täglich 
zusammen, was etwa dreißig Mediatheken anbieten: knapp 594.000 Einträge, jeder mit Sender, 
Thema, Titel und den Links zum Video und zur Sendungsseite. Wenn undokumentierte Schnittstellen
sich ändern, dann steuern die Maintainer aktiv nach und stellen den fortlaufenden Betrieb sicher.
Damit leisten die Maintainer eine sehr wertvolle Grundarbeit.

Wer ein Softwareprojekt mit Bezug zu Mediatheken baut, fragt deshalb in der Regel nicht selbst
bei den Sendern nach, sondern verwendet die Filmliste als Grundlage. Rund 80 öffentliche Projekte 
bauen darauf auf (eigene Zählung).

Was in dieser Filmliste steht, sieht also fast jedes Programm, das Mediatheken senderübergreifend durchsucht. 
**Umgekehrt gilt: Was dort fehlt, fehlt überall**.

Schauen wir etwas genauer auf Merkmale zur Barrierefreiheit: Die Filmliste sieht hier keine eigenen 
Spalten oder Datenfelder vor, die Merkmale werden (wenn überhaupt) als Freitext im Filmtitel erfasst.
Bei der Hörfassung geht das meistens gut, weil auf dem Weg in die Filmliste zumindest ein entsprechendes 
Wort in den Titel geschrieben wird (wenn auch kein eindeutiges). 

Andere Merkmale kommen gar nicht an. Die ARD-Mediathek liefert Klare Sprache oft als zusätzliche Datei 
neben der normalen Fassung. In der Filmliste steht keine einzige dieser Dateien. ARTE bietet Untertitel
für Hörgeschädigte an. In der Filmliste steht keine einzige Adresse dazu. Die Sender halten diese 
Angaben bereit, jeder in seinem eigenen Format und ohne offene Dokumentation und ohne Zusage, dass
es morgen noch so ist. Wer das einsammelt, muss für jeden Sender eigens nachbauen, was
dieser gerade tut. Was dabei nicht nachgebaut wird oder übersehen wird, das fehlt in der Filmliste und
damit in allen Programmen, die auf ihr aufbauen.

Wer bemerkt die Lücke, wenn eine Information auf diesem Weg verloren geht? Fast niemand. Wer gut sieht
und hört, braucht diese Fassungen nicht und sucht nicht nach ihnen. Wer sie braucht, bekommt von seinem
Programm ein „gibt es nicht“ und kann nicht selbst prüfen, ob das stimmt. Es gibt für dieses Szenario 
keine Fehlermeldung, und wer nicht weiß, dass etwas fehlt, beschwert sich nicht. So bleibt ein bezahltes
Angebot bei den Menschen unsichtbar, für die es gemacht ist, und in keiner Statistik taucht das auf.

Alle nachfolgenden Beispiele sind verlinkt, damit sich jeder selbst ein Bild machen kann. Mediatheken nehmen
Sendungen nach Ablauf der Rechte wieder heraus; ein Link kann deshalb irgendwann ins Leere
führen. Zum Zeitpunkt der Erstellung dieses Textes haben die Links funktioniert (30.09.2026).

---

## Datenqualität an der Quelle: beim Sender

Für sich genommen schreibt jeder Sender meist einheitlich. Das Durcheinander entsteht
zwischen den Sendern. Ein Merkmal wie „Hörfassung“ kann an vier Orten stehen, und jeder
Sender benutzt andere:

| Ort | Beispiel | Kommt in der Filmliste an? |
|---|---|---|
| **Titel** der Sendung | „(klare Sprache)“ beim WDR | ja, als Freitext |
| **Seitenadresse** | `…/videos/audiodeskription/…` bei KiKA | ja, aber nur als Link |
| **Dateiname** des Videos | `_internationalerton_` bei „Donuts“ | ja, aber nur als Link |
| **Datenfeld** der Schnittstelle | `["UT","AD","DGS"]` bei der ARD | nein |

Die folgenden Beispiele zeigen, was die Sender an diesen vier Orten tun. Jedes ist echt,
alle sind verlinkt. „Sender“ meint in den Tabellen das Senderfeld der Filmliste. Dort
stehen die ARD und ihre Landesrundfunkanstalten wie der BR nebeneinander, obwohl alles
aus der ARD-Mediathek kommt.

### Ein Tatort, vier Einträge und ein falsches Versprechen

„Die ewige Welle“ steht viermal in der Filmliste:

| Sender | Titel |
|---|---|
| ARD | „[Tatort: Die ewige Welle](https://www.ardmediathek.de/video/Y3JpZDovL3N3ci5kZS9hZXgvbzE4NzUzNjA)“ |
| ARD | „[Tatort: Die ewige Welle **- Audiodeskription**](https://www.ardmediathek.de/video/Y3JpZDovL3N3ci5kZS9hZXgvbzE4NzUzNjE)“ |
| BR | „[Tatort: Die ewige Welle](https://www.ardmediathek.de/video/Y3JpZDovL2JyLmRlL2Jyb2FkY2FzdC9GMjAxOVdPMDEwMDIyQTA)“ |
| BR | „[Tatort: Die ewige Welle **(Hörfassung)**](https://www.ardmediathek.de/video/Y3JpZDovL2JyLmRlL2Jyb2FkY2FzdC9GMjAxOVdPMDEwMDIyQTAvc2VjdGlvbi84ZDE4YWE4Yi1hYjcyLTRhN2QtOWNkNi1hNDlkZTVhZmQxOWI)“ |

Eine Hörfassung, zwei Schreibweisen für sie, einmal mit Bindestrich, einmal in Klammern.
Das „(Hörfassung)“ im letzten Eintrag schreibt der Sender selbst, so heißt die Seite in der
ARD-Mediathek. Und für genau diese Seite meldet dieselbe ARD-Mediathek im Datenfeld:
**keine Audiodeskription.** Der Titel sagt ja, das Datenfeld sagt nein, beides aus einer
Quelle. Wer sich auf das Wort verlässt, startet den Film und hört keine Bildbeschreibung.

### Drei Wörter für eine Sache in einem einzigen Eintrag

Bei KiKA heißt eine Folge von „Addie und wie sie die Welt fühlt“
„[5. Fatale Partys **(Hörfassung)**](https://www.kika.de/addie-und-wie-sie-die-welt-fuehlt/videos/audiodeskription/fatale-partys-als-hoerfilm-100)“.
Ihre Seitenadresse lautet `…/videos/`**`audiodeskription`**`/fatale-partys-als-`**`hoerfilm`**`-100`.
Hörfassung, Audiodeskription, Hörfilm: dasselbe Merkmal, dreimal anders, in einem Eintrag.

### Die Hörfassung heißt „internationaler Ton“

Beim Tatort „[Donuts](https://www.ardmediathek.de/video/Y3JpZDovL2Rhc2Vyc3RlLmRlL3RhdG9ydC8yMDIzLTA0LTAyXzIwLTE1LU1FU1o)“
liegen normale Fassung und Hörfassung als zwei Dateien auf derselben Seite. Sichtbar ist
das nur im Dateinamen: Die
[normale Fassung](https://ctv-videos.daserste.de/int/2023/03/22/f22a2099-ac0e-4718-9616-a3ee474cfe7f/JOB_568979__sendeton_1280x720-50p-3200kbit.mp4)
heißt `…_sendeton_…`, die
[Hörfassung](https://ctv-videos.daserste.de/int/2023/03/22/f22a2099-ac0e-4718-9616-a3ee474cfe7f/JOB_568980__internationalerton_1280x720-50p-3200kbit.mp4)
`…_`**`internationalerton`**`_…`.

Beim Tatort „Haus der Toten – Tod am Rennsteig“ heißt die Datei mit der Hörfassung
`…_audiodeskription_…`. Beim Tatort „Licht“ (HR) heißen alle drei Dateien `…_sendeton_…`:
die normale Fassung, die Hörfassung und die Fassung mit Gebärdensprache. Dieselbe Sache,
drei Namen.

Manche Häuser legen außerdem eine zweite Seite an, deren Seitendresse auf „/audiodeskription“
endet (Tatort „Licht“, HR:
[normal](https://www.ardmediathek.de/video/MzlkYWUyNGQtYTliMi00ZTVkLTg5MzMtMWU3NTk4ZDJlYzYz),
[„/audiodeskription“](https://www.ardmediathek.de/video/MzlkYWUyNGQtYTliMi00ZTVkLTg5MzMtMWU3NTk4ZDJlYzYzL2F1ZGlvZGVza3JpcHRpb24);
Tatort „Unter Feuer“, MDR:
[normal](https://www.ardmediathek.de/video/Y3JpZDovL21kci5kZS9zZW5kdW5nLzI4MjA0MC81MTQ0NzgtNDk0NDk5),
[„/audiodeskription“](https://www.ardmediathek.de/video/Y3JpZDovL21kci5kZS9zZW5kdW5nLzI4MjA0MC81MTQ0NzgtNDk0NDk5L2F1ZGlvZGVza3JpcHRpb24)).
Beide Seiten liefern dieselben Dateien. Wer Seiten zählt, sieht zwei Sendungen, wo eine ist.

### Klar ist nicht einfach

„Klare Sprache“ und „Einfache Sprache“ klingen fast gleich und haben nichts miteinander zu tun:

- **Einfache Sprache / Leichte Sprache** verändert den **Text**: kürzere Sätze, einfachere
  Wörter. Beispiel: die tägliche „tagesschau in Einfacher Sprache“.
- **Klare Sprache** verändert den **Ton**: Musik und Geräusche leiser, Dialog lauter, die
  Wörter bleiben gleich. Sie hilft Menschen, die schlecht hören.

Beim WDR steht Klare Sprache als eigene Datei mit „(klare Sprache)“ im Titel, etwa beim Tatort
„[Die letzten Menschen von Köln](https://www.ardmediathek.de/video/Y3JpZDovL3dkci5kZS9CZWl0cmFnLXNvcGhvcmEtYjM2NzBlNDMtOTBmMC00YTQxLWE5M2QtNTlhYWU3NGI0N2Ew)“.
In der ARD-Mediathek liegt sie außerdem als eigene Datei neben der normalen Fassung, etwa bei
„[Haus der Toten – Tod am Rennsteig](https://www.ardmediathek.de/video/Y3JpZDovL2FyZC5kZS9wbGFuQVJEX2E2MjNhM2FmLTA2MTctNDA3Mi1hODFiLWZiZjVhMjE5NGVlM19nYW56ZVNlbmR1bmc)“
(`…_klaresprache_…`), ohne eigenen Titel und ohne eigene Seite. Dasselbe Merkmal also
einmal im Titel, einmal nur im Dateinamen. Eine Datei kann auch beides zugleich sein:
„[Tatort: Diesmal ist es anders **(klare Sprache) (Audiodeskription)**](https://www.ardmediathek.de/video/Y3JpZDovL3dkci5kZS9CZWl0cmFnLXNvcGhvcmEtNWQ1ZWYzYWMtYjFiZS00ODU5LThhMDAtYjk3ZGMzZmFmYzFm)“.

Eine Suche, die beide Begriffe zusammenwirft, schickt einen schwerhörigen Menschen zu
Nachrichten in vereinfachter Sprache.

### Eine Hörfassung, die man nicht versteht

Auf der deutschen ARTE-Seite von
„[Das U-Boot (1/2)](https://www.arte.tv/de/videos/095101-001-A/das-u-boot-1-2/)“ gibt es die
Hörfassung nur auf **Französisch**.

### Deutsch oder Französisch?

„[Die Prinzessin von Cleve](https://www.arte.tv/de/videos/025621-000-A/die-prinzessin-von-cleve/)“
hat bei ARTE zwei Hörfassungen, eine deutsche und eine französische. Auf der deutschen Seite
heißt die deutsche „Deutsch (Hörfilm)“. Ihre Kurzbezeichnung lautet aber **„AD (frz.)“**,
genau wie die der französischen. Auf der
[französischen Seite](https://www.arte.tv/fr/videos/025621-000-A/la-princesse-de-cleves/)
heißt dieselbe deutsche Hörfassung „Allemand (audiodescription)“, kurz „AD DE“.

### Fünf Sender, fünf Arten, „ja“ zu sagen

*Für Technikinteressierte*: Hinter den Kulissen *haben* die Sender die Merkmale strukturiert. Nur eben jeder 
anders, und keiner über eine offene, dokumentierte Schnittstelle:

| Sender | So sagt er „hat eine Hörfassung“ | So heißt das Ablaufdatum |
|---|---|---|
| ARD | eine Aufzählung von Kürzeln: `["UT","AD","DGS"]` | `availableTo` |
| ZDF | ein Feld, dessen bloßes *Vorhandensein* „ja“ bedeutet | `visibleTo` |
| ARTE | je Sprachfassung ein Schalter `audioDescription` | `rights.end` |
| KiKA | `hasAdVideo: true` | `endDate` |
| PHOENIX | ein Kürzel am Sendetermin (`ut`, `gs`, `zk`) | `visibleTo` |

Die Sprache schreibt die ARD mit drei Buchstaben (`deu`), ARTE mit zwei (`de`). Bei 16 Sendungen
meldet die ARD-Mediathek im Datenfeld statt einer Sprache nur „ov“ ("Originalversion"), welche auch immer, etwa
bei der Serie „[Soul Shift](https://www.ardmediathek.de/video/MDU1NjQyNGEtNGU4ZS00MTg4LTllNWMtNzFiZWE0NjNlNTgy)“.
Und ARTE benennt dieselbe Fassung je nach Sprache der Anfrage anders: „OmU-POL“ auf Deutsch,
„POL“ auf Polnisch.

Vollständig ist diese Aufstellung sicher nicht. Sie beruht auf eigener Untersuchung und auf Stichproben. Eine 
öffentliche Dokumentation, auf die ich mich stützen könnte, gibt es nicht.

---

## Datenqualität in der Filmliste

Die Filmliste kennt für jede Sendung Sender, Thema, Titel und die Links zu Seite und
Videodatei. Ein eigenes Feld für Barrierefreiheit gibt es nicht. Alles, was die Sender an
den vier Orten oben hinterlegen, muss deshalb beim Sammeln zu einem Wort im Titel werden,
oder es geht verloren. Dabei passieren drei Dinge: Wörter werden hinzugefügt, Wörter werden
ersetzt, und Merkmale bleiben manchmal auch auf der Strecke.

### Wer schreibt das Wort in den Titel?

Oft nicht der Sender. In der ARD-Mediathek heißt die Folge schlicht „Donuts“; erst auf dem
Weg in die Filmliste wird daraus „Donuts (Audiodeskription)“. Bei funk schreibt der
Sender „… | Hörfassung | 100percentme“, in der Filmliste steht daraus
„[… | Audiodeskription | 100percentme](https://www.ardmediathek.de/video/Y3JpZDovL2Z1bmsubmV0LzEyMDA0L3ZpZGVvLzE2NTA2NTM)“
– das Wort wird mitten im Titel ausgetauscht. 

Und im spanischen ARTE-Kanal heißt die Folge bei ARTE schlicht „Camaradas (2/8)“. In der
Filmliste steht „[Camaradas (2/8) **(Originalversion mit Untertitel)**](https://www.arte.tv/es/videos/123309-002-A/camaradas-2-8/)“:
ein deutscher Zusatz, den die Filmliste an einen spanischen Titel hängt.

Manchmal bleibt von einer solchen Ersetzung nur eine Hülle. In der Filmliste
stehen Titel wie
„Eisige Schatten – Folge 3 (S01/E03) **()** (Audiodeskription)“: leere Klammern, der Rest
einer automatischen Umbenennung.

### Gebärdensprache in fünf Schreibweisen

In der Filmliste steht Gebärdensprache als „(Gebärdensprache)“, „(mit Gebärdensprache)“,
„(Mit Gebärdensprache)“, „(DGS)“ und
„[Die Sendung vom 23.09.2022 **mit Deutscher Gebärdensprache (DGS)**](https://www.ardmediathek.de/video/Y3JpZDovL3N3ci5kZS9hZXgvbzE3MzA3MjQ)“.
Ein Teil davon kommt vom Sender: Die ARD-Mediathek schreibt „(mit Gebärdensprache)“, der
SWR „mit Deutscher Gebärdensprache (DGS)“. Das kurze „(Gebärdensprache)“ hängt die
Filmliste an, auch dort, wo der Sender gar nichts in den Titel schreibt. Im Datenfeld der
ARD-Mediathek heißt dieselbe Sache schlicht `DGS`. Wer alle Fassungen mit Gebärdensprache
finden will, muss fünf Schreibweisen kennen und weiß trotzdem nicht, ob er alle hat.

### Vertauscht

Vom Tatort „Siebte Etage (2024)“ gibt es in der ARD-Mediathek eine Seite, deren Seitenadresse auf
„/audiodeskription“ endet, und eine, die auf „/gebaerdensprache“ endet. Beim Sender stimmt
alles: Die erste heißt „Siebte Etage (2024) (Audiodeskription)“, die zweite
„Siebte Etage (2024) (mit Gebärdensprache)“.

In der Filmliste steht es umgekehrt:

| Seitenadresse endet auf | Titel in der Filmliste |
|---|---|
| [/audiodeskription](https://www.ardmediathek.de/video/Y3JpZDovL3dkci5kZS9CZWl0cmFnLXNvcGhvcmEtZGRiYzBlYWQtNjNhMi00MTY4LThlZWYtZmE5NGUxNzM0NmY5L2F1ZGlvZGVza3JpcHRpb24) | „Siebte Etage (2024) **(Gebärdensprache)**“ |
| [/gebaerdensprache](https://www.ardmediathek.de/video/Y3JpZDovL3dkci5kZS9CZWl0cmFnLXNvcGhvcmEtZGRiYzBlYWQtNjNhMi00MTY4LThlZWYtZmE5NGUxNzM0NmY5L2dlYmFlcmRlbnNwcmFjaGU) | „Siebte Etage (2024) **(Audiodeskription)**“ |

Diesmal geht es gut aus, weil beide Seiten ohnehin alle drei Fassungen liefern. 
Verlassen kann sich darauf niemand: Solche vertauschten Einträge stehen über 
hundertmal in der Filmliste (109 am 30.09.2026).

### Untertitel, die es gibt und die nirgends ankommen

ARTE führt Untertitel ausdrücklich „für Hörgeschädigte“, etwa „Deutsch (Hörgeschädigte)“ beim
U-Boot. In der Filmliste steht für ARTE **kein einziger** Link zu einer Untertiteldatei. Der Grund ist
dokumentiert und technisch: ARTE liefert die Untertitel samt Kennzeichnung „für
Hörgeschädigte“ über seine Schnittstelle, der Crawler von MediathekView liest diese Angaben
auch ein, verwirft sie aber. Der Einbau würde einen zweiten Abruf je Sendung erfordern, und
das verträgt sich nicht mit dem Anfragelimit von ARTE und der Laufzeit des Crawlers
([Issue #791](https://github.com/mediathekview/MServer/issues/791), offen seit Januar 2022).
Die Untertitel gibt es, sie sind markiert, und sie kommen trotzdem nicht an.

Genauso geht es den Klare-Sprache-Dateien der ARD-Mediathek: Sie liegen als zweite Videodatei neben der
normalen Fassung, und kein einziger Eintrag der Filmliste verweist auf eine davon. Was der
Sender nur im Dateinamen oder im Datenfeld hinterlegt, erreicht die Filmliste nicht.

Bei PHOENIX ist es anders herum: Dort fehlen die Untertitel schon beim Sender. In rund 8.000
Antworten der ARD-Mediathek zu PHOENIX-Sendungen findet sich keine einzige. Immerhin ist
das „Nein“ dort durchgehend korrekt, weil es gar nichts zu verlieren gab.

### Dieselbe Folge, zwei Nummern

Die „Rentnercops“ stehen unter derselben Seitenadresse einmal als
„[Folge 3: Altes Eisen](https://www.ardmediathek.de/video/Y3JpZDovL3dkci5kZS9CZWl0cmFnLTNlZjMwNjE2LTI0MDQtNGU1NS05NWZlLTZlMjZhYzJjODM5Ng)“
(Sender ARD) und einmal als „Folge 43: Altes Eisen“ (Sender WDR). Die Hörfassung hängt nur am
zweiten Eintrag. Wer nach Folge 3 sucht, findet sie nicht.

### Wörter, die täuschen

Am Ende der Kette stehen die Programme, und die haben nur noch den Titel. Was ein Wort
im Titel bedeutet, müssen sie raten:

„[In der Tonkabine: So entstehen Hörfilme](https://www.ardmediathek.de/video/Y3JpZDovL21kci5kZS9iZWl0cmFnL2Ntcy9lNTcwOTAzMS00MWI1LTQ4OGEtYmFjYy04ZWM4NzEyMjhhMzI)“
ist ein Beitrag über Hörfilme, aber selbst keiner.
„[Leichte Sprache braucht fast jeder zehnte Mensch](https://www.ardmediathek.de/video/Y3JpZDovL3N3ci5kZS9hZXgvbzIwNzc3MjE)“
ist ein Beitrag *über* Leichte Sprache, nicht *in* ihr. Ein verbreitetes Programm wertet schon
„AD |“ oder „Hörspiel“ im Titel als Hinweis auf eine Hörfassung und kündigt so
„[Das Ende von THE WALKING DE**AD |** TOP 5](https://www.ardmediathek.de/video/Y3JpZDovL2Z1bmsubmV0LzExNjY0L3ZpZGVvLzE3NTg4MDk)“
oder „[Die Pfefferkörner gibt's auch als **Hörspiel**!](https://www.ardmediathek.de/video/Y3JpZDovL25kci5kZS80NzFhMzkyNy0zZTZmLTRhNGYtYTU5Ny02OGI2NGE3ZDU1Yjg)“
als Hörfassung an.

---

## Was daraus folgt: Ja, Nein und ungeprüft

Ein Wort im Titel kann nur „ja“ sagen. **Ein fehlendes Wort ist kein Nein.** Steht nichts im
Titel, weiß man nur, dass nichts dasteht. Ein barrierefreies Merkmal hat deshalb drei
Zustände:

- **ja**: der Sender bestätigt es, oder es gibt die Datei
- **nein**: der Sender wurde gefragt und verneint
- **ungeprüft**: niemand hat gefragt

Die meisten Suchen kennen nur „gefunden“ und „nicht gefunden“ und machen aus jedem
„ungeprüft“ stillschweigend ein „nein“. 

Steht auf einer Speisekarte nichts von Nüssen, verlässt sich niemand darauf, dass das Gericht nussfrei 
ist. Steht in der Filmliste nichts von einer Hörfassung, bleibt jedem Programm aber nichts anderes 
übrig, als genau das anzunehmen.

Dazu kommt die Zeit: Sendungen verschwinden wieder aus den Mediatheken. Die Sender kennen
das Ablaufdatum, die Filmliste hat dafür kein Feld. Wer nicht selbst durch eine
Mediathek scrollen kann, erfährt nie, dass eine Hörfassung morgen weg ist.

---

## Was die Messung zeigt

Eigene Messung, Stand 30.09.2026: die Filmliste und
12.561 einzelne Nachfragen bei den Sendern. Gezählt wird jede Sendung einmal, nicht jeder Eintrag. Eine Folge steht oft zweimal in der Filmliste, als „Donuts“ und als „Donuts (Audiodeskription)“. Wer die Einträge einzeln prüft, findet beim ersten keinen Hinweis und meldet eine fehlende Kennzeichnung, obwohl die Hörfassung gleich daneben steht.

- **Keine** Sendung mit Hörfassung in der Sprache ihres Kanals ist in der
  Filmliste ganz unauffindbar (0 von 441), aber vier nur unter einem anderen Sender, Thema oder Folgentitel.
- **18** Sendungen haben eine Hörfassung nur in einer anderen Sprache.
- Für **9.465** Sendungen hat der Sender ausdrücklich verneint, dass es eine Hörfassung gibt.
  In der Filmliste sehen sie aus wie Sendungen, nach denen nie jemand gefragt hat.

Die Häufigkeit der Lücke ist also nicht das Hauptproblem. Das Hauptproblem ist die
Konstruktion: Ein Wort im Titel kann nicht sagen, was geprüft fehlt, was bald verschwindet,
welche Tonspur in einer Datei steckt und in welcher Sprache eine Fassung vorliegt.

Repräsentativ ist die Stichprobe nicht. Sie besteht aus gezielten Suchläufen, zum Beispiel nach dem Tatort, den 
jeweils neuesten Adressen und dem ganzen Sender PHOENIX in der ARD-Mediathek und deckt 
rund 3 % der abfragbaren Adressen ab. 

---

## Zwei Ursprünge, zwei Adressaten

| Ursprung | Beispiele | Wer könnte es lösen |
|---|---|---|
| **beim Sender** | verschiedene Formen der Hörfassung; unterschiedliche Feldnamen und Sprachcodes; Hörfassung nur in einer Fremdsprache; „Klare Sprache“ als verwechselbarer Name; keine offene, dokumentierte Schnittstelle | die Sender |
| **auf dem Weg zu den Programmen** | Merkmal nur als Titelwort; vertauschte oder leere Zusätze; kein Feld für Tonspuren, Ablaufdatum oder ein geprüftes Nein; verlorene Untertitel; dieselbe Sendung unter verschiedenen Sendern, Themen oder Folgennummern | alle, die Mediathekdaten sammeln und weitergeben |

Eins ist mir dabei wichtig: Die Filmliste wird seit über 18 Jahren ehrenamtlich gepflegt. Ohne sie gäbe es für Dritte gar keinen praktikablen Zugang zu den Mediatheken. Die Schnittstellen der Sender ändern sich regelmäßig, und jedes Mal muss das Team nachsteuern. Das ist wertvolle Arbeit, und ich habe großen Respekt davor.

Diese Analyse will die Filmliste nicht ersetzen, sondern sucht nach Wegen zur Ergänzung.

---

## Warum macht MediathekView das nicht selbst?

Naheliegend wäre, dass MediathekView die fehlenden Angaben einfach ergänzt. Ein paar Felder
mehr, und die Hörfassung hätte ihr eigenes? Warum das bisher nicht geschehen ist, können
nur die Maintainer sagen. Von außen sichtbar sind vier Grenzen, an denen jede Erweiterung
vorbeimuss, und keine davon hat das Projekt selbst gesetzt.

**Die Quellen.** Die Filmliste kann nur weitergeben, was die Sender hergeben, und die geben
es jeder anders her: als Wort im Titel, als Teil der Seitenadresse, als Dateiname, als
Datenfeld. Keine dieser Schnittstellen ist offen dokumentiert, und sie ändern sich ohne
Ankündigung. Die Commit-Geschichte des Crawlers zeigt das: zwischen 35 und 90 Änderungen am
Senderteil pro Jahr, meist um die 50, und in acht der neun Jahre seit 2018 musste
mindestens ein Sender komplett neu angebunden werden, zuletzt das ZDF 2025 mit seiner
neuen Mediathek (Stand Oktober 2026). Das ist keine Weiterentwicklung, das ist Nachsteuern.
Jedes neue Feld wäre eine weitere Stelle, die bei jeder Senderänderung mitbricht.

**Der Betrieb.** Der Crawler fragt mehrmals täglich rund dreißig Mediatheken ab, und die
Sender begrenzen, wie oft er das darf. Die ARTE-Untertitel zeigen, was das heißt: Der
Crawler liest sie samt Kennzeichnung „für Hörgeschädigte“ bereits ein. Sie in die Filmliste
zu bringen, bräuchte einen zweiten Abruf je Sendung, und der passt nicht in das Anfragelimit
von ARTE und die Laufzeit des Crawlers
([Issue #791](https://github.com/mediathekview/MServer/issues/791), offen seit 2022).
Ein geprüftes Nein wäre noch teurer: Wer „nein“ sagen will, muss bei jeder Sendung
nachfragen und die Antwort festhalten. Wer „bis wann“ sagen will, muss das Ablaufdatum
mitführen und aktuell halten. Das ist eine andere Aufgabe als das Sammeln.

**Die Verträglichkeit.** Die Filmliste ist rund fünfzehn Jahre alt. Jeder Eintrag ist eine
Reihe von zwanzig Werten in fester Reihenfolge, ohne Feldnamen. Viele Werkzeuge Dritter
lesen sie genau so: Position für Position. Deshalb wird das Format bewusst stabil gehalten.
Neue Felder lassen sich hinten anhängen, alte lassen sich nicht umbauen. Ein Bruch träfe
Menschen, die nichts falsch gemacht haben. Dazu kommt die Größe: Unkomprimiert ist die
Liste etwa ein Gigabyte groß, und viele Installationen laden sie täglich. Jedes zusätzliche
Feld kostet Datenverkehr, den jemand bezahlt.

**Das Risiko.** 2020 wurde MediathekView wegen eines einzelnen Films abgemahnt, obwohl die
Filmliste nur Links enthält und nie eine Videodatei. Die Anwaltskosten trug das Projekt aus
Spenden. Wer ehrenamtlich Daten der Sender weitergibt, trägt dieses Risiko allein. Auch das
spricht nicht dafür, immer mehr Angaben einzusammeln, für die sich kein Sender zuständig
fühlt.

Die Erweiterungen werden trotzdem aktiv diskutiert. Im Entwicklungszweig führt das
Datenmodell Hörfassung und Gebärdensprache schon als eigene Felder. Für die Sprache der
Tonspur liegen zwei fertige Änderungsvorschläge vor, für die
[ARD](https://github.com/mediathekview/MServer/pull/1174) und das
[ZDF](https://github.com/mediathekview/MServer/pull/1175), mit Tests und dem Nachweis, dass
bestehende Programme das neue Feld schadlos überspringen. Übernommen sind sie bisher nicht
(Stand 20.10.2026). Das ist eine konservative Entscheidung der Maintainer, und sie ist zu
respektieren: 

Ob und wann sie übernommen werden, entscheiden die Maintainer, und das ist zu respektieren:
Wer ein Format verantwortet, von dem rund achtzig Projekte abhängen, hat gute Gründe, mit
jeder Änderung vorsichtig zu sein.

Entscheidend ist aber etwas anderes: Selbst wenn alle diese Felder morgen in der Filmliste
stünden, wären sie Rekonstruktionen aus fünf undokumentierten Quellen. Ein Feld kann nicht
besser sein als das, was die Sender liefern. Solange jeder Sender anders antwortet, bleibt
auch die beste Filmliste Nacharbeit an Einzelfällen, geleistet von Ehrenamtlichen, die dafür
weder Auftrag noch Zusage der Sender haben. Für Menschen, die eine Hörfassung suchen, heißt
das heute: Die Auskunft bleibt ein Wort im Titel. Die Ursache dafür liegt nicht bei denen,
die das Wort hineinschreiben.

Was auch für sich spricht: Ein Fork des Crawlers ist technisch einfach, MServer ist frei. 
Tatsächlich zeigt GitHub 21 Forks. Aber keiner davon schafft es in den Regelbetrieb und 
erzeugt eine eigene Filmliste. Dass es in zehn Jahren niemand getan hat, zeigt, dass die
Hürde nicht der Code ist, sondern der Betrieb: eigene Server, die Anfragelimits der Sender,
das Nachsteuern bei jeder Senderänderung und das Abmahnrisiko.

---

## Es fehlt kein Standard

- **TV-Anytime** (ETSI TS 102 822): die europäische Norm der Rundfunkwelt. Mit ihr
  kennzeichnet der Rundfunkstandard DVB Hörfassung und Klare Sprache, auch im
  Internet-Fernsehen (DVB-I).
- **schema.org**: das gemeinsame Vokabular des Webs, das Suchmaschinen verstehen. Seine
  Merkmale zur Barrierefreiheit sind für barrierefreie E-Books bereits Pflicht (W3C,
  EPUB Accessibility 1.1).

Was fehlt, ist die Übersetzung zwischen den Welten. Und wo ein Standard schweigt, muss man das
klar sagen: schema.org kennt zum Beispiel keinen Wert für Klare Sprache.

**Zuständig ist niemand**. Die Sender bauen Mediatheken, keine Datenquelle für andere Programme.
MediathekView sammelt ehrenamtlich und muss sein Format stabil halten. Die Programme nehmen, 
was in der Filmliste steht, und raten den Rest. Jeder Beteiligte handelt nachvollziehbar.
Zusammen ergibt das eine Lücke, für die sich niemand zuständig fühlt.

---

## Was es bräuchte

Dass die Sender ihrer Aufgabe nachkommen. Sie produzieren die barrierefreien Fassungen,
sie wissen, was sie haben, und sie sind gesetzlich verpflichtet, barrierefreie Angebote
zugänglich zu machen. Der fehlende Schritt ist eine **gemeinsame, offene Schnittstelle**,
die für jede Sendung sagt, welche Fassungen es gibt, in welcher Sprache, wie ausgeliefert
und bis wann. Ein Vokabular, fünf Sender, eine Antwort. Die Standards dafür gibt es.

Solange es das nicht gibt, braucht es eine Überbrückung: ein **offenes Werkzeug**, mit dem
sich jeder diese Auskunft selbst erzeugen kann, als Ergänzung neben der Filmliste, mit
drei Antworten statt zwei: **ja, nein und ungeprüft.** Keine neue Mediathek, keine neue
App, kein zweiter Crawler, und kein neuer Dienst, der einen Betreiber braucht. Wer das
Werkzeug laufen lässt, hat die Datei. Wer sie veröffentlicht, erspart anderen das
Nachfragen beim Sender. Betreiber kann jeder werden, auch die Sender selbst.

Darum müsste sich jemand kümmern. Und zwar um drei Dinge:

- **Um ein gemeinsames Vokabular.** Fünf Sender sagen auf fünf Arten „ja“. Jemand muss
  diese fünf Arten auf einen Wert abbilden, dokumentiert und nachprüfbar, in den Standards,
  die es schon gibt. Diese Abbildung ist zugleich der Vorschlag an die Sender, wie ihre
  gemeinsame Schnittstelle aussehen könnte: Das Format, das das Werkzeug ausgibt, ist das
  Format, das die Sender liefern müssten. Nicht als neuer Standard, sondern als
  Diskussionsbeitrag auf Grundlage der bestehenden, geprüft an echten Daten und an jedem
  Fall in diesem Dokument.
- **Um geprüfte Aussagen statt Wörter im Titel.** Jemand muss bei den Sendern nachfragen,
  die Antworten festhalten, auch ein Nein, und dazusagen, wie vollständig die Auskunft ist.
  Schonend erhoben: nur gezielt, nur für Neues, und fremde Ergebnisse werden eingelesen
  statt erneut erfragt. Ohne eigenen Bestand an Inhalten. Als freie Software, die auf
  einem Raspberry Pi läuft.
- **Um Zahlen.** Niemand weiß heute öffentlich, wie viele barrierefreie Fassungen produziert werden
  und wie viele davon auffindbar sind. Die Messung oben ist ein erster Lauf. Jeder Lauf des
  Werkzeugs liefert sie neu, je Sender, mit Datum. Wer sie veröffentlicht, macht sichtbar,
  was fehlt, auch für die Sender.

Ein großer Teil dieser Arbeit ist keine Programmierung. Sie besteht darin, jeden der oben
gezeigten Fälle zu finden, zu prüfen und sauber einzuordnen, und jeden neuen Fall, den
Betroffene melden, dazu. Aus einer Sammlung von Ärgernissen wird so ein Prüfstand.

Diese Lücke schließt sich nicht von selbst. Es fehlt jemand, der die Angaben der Sender
zusammenführt und dafür geradesteht, dass die Methode stimmt: dass jeder bekannte Fall
richtig eingeordnet wird, auch wenn die Antwort „nein“ lautet. Bis die Sender es selbst
tun. Das Ziel der Überbrückung ist, überflüssig zu werden.

---

## Wer dahintersteht

Ich bin Frank Börncke, freiberuflicher Softwareentwickler. Seit 2020 betreibe ich kostenlos
„[Meine Mediathek](https://www.meinemediathek.de)“, eine Alexa-Sprachanwendung, mit der man
die Mediatheken von ARD, ZDF und ARTE per Sprache durchsuchen und abspielen kann, auch ohne
Bildschirm. In dem mehrjährigen Betrieb habe ich gelernt, wo die Grenzen der heutigen
Datenlage liegen, gerade beim barrierefreien Zugang. Die Messung in diesem Dokument, die
Nachfragen bei den Sendern und die Änderungsvorschläge an MediathekView sind daraus
entstanden. Wie ich die drei Punkte oben angehen will, beschreibe ich im Antrag.

Dieses Vorhaben hat keine Gewinnabsicht. Es versteht sich als **Diskussionsbeitrag** in
zwei Richtungen: Es zeigt, dass Auffindbarkeit technisch möglich ist, und es liefert Zahlen,
wo bisher niemand welche hatte. Und es legt ein Format vor, an dem sich diskutieren lässt,
wie eine gemeinsame Auskunft der Sender aussehen könnte.

**Kontakt und Hinweise** sind willkommen, besonders von Menschen, die Hörfassungen,
Gebärdensprache oder Klare Sprache selbst nutzen, und von Projekten, die Mediathekdaten
verarbeiten.

---

*Alle Beispiele und Zahlen: eigene Untersuchung, Stand 30.09.2026. Die Mediathekdaten ändern
sich täglich. Die Links in die Mediatheken haben zum Zeitpunkt der Veröffentlichung
funktioniert.*
