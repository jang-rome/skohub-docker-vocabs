<a name="0"></a>
# Publikation eines kontrollierten Vokabulars mit SkoHub Vocabs

Projektbericht Modul MALIS 23.2 IT 2
Dozent: Adrian Pohl

**Arbeitsgruppe:**

Regina Sofia Margarete Albrecht (Matrikelnummer: 11188249 ), Email: Regina_sofia_margarete.albrecht@smail.th-koeln.de

Jonas Balzukat (Matrikelnummer: 11096598 ), Email: Jonas.Balzukat1@smail.th-koeln.de

Jan-Peter Grünewälder  (Einzelmodulbucher), Email: grunewalder@dhi-roma.it

## Inhalt
- [1. Auswahl des kontrollierten Vokabulars und Entwicklung einer Projektidee](#1)
	- [1.1 Bibliothek](#1.1)
	- [1.2 Digital Humanities und Institutspublikationen](#1.2)
	- [1.3 Entwicklung der Projektidee](#1.3)	
- [2. Organisation der Zusammenarbeit](#2)
- [3. Stufenweise Umsetzung der SKOS-Transformation](#3)
	- [3.1 Erarbeitung eines validierten SKOS-Grundgerüsts](#3.1)
	- [3.2 Erarbeitung eines Verfahrens zur semiautomatisierten Transformation](#3.2)
	- [3.3 Einrichtung langfristig verfügbarer URI (Purl.org)](#3.3)
    - [3.4 Finale Bearbeitung Gesamtvokabular und SkoHub-Publikation](#3.4)
- [4. Ausblick](#4)
- [5. Anhang: Python-Skript zur semiautomatisierten SKOS-Transformation](#5)

  
  
<a name="1"></a>
## 1. Auswahl des kontrollierten Vokabulars und Entwicklung einer Projektidee

Zu Beginn des Projekts wurde das am Deutschen Historischen Institut Rom (DHI) eingesetzte kontrollierte Vokabular identifiziert. Es erstreckt sich zum einen auf verschiedene bibliothekarische Klassifikationen und zum anderen auf Vokabular, das seit 2004 im Kontext der Digital Humanities entstanden ist.
<a name="1.1"></a>
### 1.1 Bibliothek
Die Bibliothek vereint zwei große wissenschaftliche Bestände der Musik- und Geschichtswissenschaft mit insgesamt ca. 300.000 Medieneinheiten. Sie werden seit 2017 organisatorisch zusammengeführt, sind aber aus historischen Gründen in zwei unterschiedlichen Fachsystematiken erschlossen und aufgestellt. Daneben integriert die Bibliothek zwei umfangreiche Spezialsammlungen zur Geschichte des italienischen Faschismus (Privatbibliothek des Journalisten und Zeithistorikers Dulio Susmel) und zur italienischen Parteiengeschichte (Privatbibliothek des Historikers Gastone Manacorda) mit eigener systematischer Erschließung ihrer ehemaligen Eigentümer.


![](https://pad.gwdg.de/uploads/5e88e834-3311-44fb-9474-9f15beb0b8e3.png)

[↑ zurück zur Übersicht](#0)
<a name="1.2"></a>
### 1.2 Digital Humanities und Institutspublikationen

Im Bereich der Digital Humanities und der Redaktionsarbeit werden fünf Vokabulare aus den digitalen Editionen und Projekten in die weitere Betrachtung einbezogen:

![](https://pad.gwdg.de/uploads/0bf87570-4419-4454-91d5-8ff950385493.png)



[↑ zurück zur Übersicht](#0)
<a name="1.3"></a>
### 1.3 Entwicklung der Projektidee

In der Analyse ergibt sich in Bezug auf die kontrollierten Vokabulare ein insgesamt unbefriedigendes Bild, d.h. das Potential kontrollierter Vokabulare wird am DHI nicht ausgeschöpft, was gerade unter den Gesichtspunkten der Sichtbarkeit und Zugänglichkeit der klassifikatorisch oder verbal erschlossenen (Daten-)Bestände ein Manko darstellt. Einige zentrale Punkte unserer Analyse in Auswahl: 

* **Normierung:** Keines der bibliothekarischen Vokabulare liegt maschinenlesbar und standardgerecht im Resource Description Framework (RDF) kodiert vor, zudem ist keines langfristig referenzierbar z.B. mittels PURL-URIs.
* **Dokumentation:** Für die Pflege und transparente Dokumentation der bibliothekarischen Vokabulare kommen keine digitalen Methoden zum Einsatz, es existieren im Wesentlichen nur gescannte PDF-Übersichten. SKOS bietet hier verschiedene relevante Dokumentations-Elemente wie skos:definition, skos:historyNote, skos:scopeNote etc. an (vgl. https://dini-ag-kim.github.io/skos-einfuehrung/#/skos-elemente?id=dokumentation).
* **Verlinkung:** Die Erschließung der Bibliotheksbestände (1.1.1 – 1.1.4) und der bibliographischen Informationsdienste (1.2.5) erfolgt bis dato ohne jegliche Verlinkung (z.B. SKOS-Mappings wie https://dini-ag-kim.github.io/skos-einfuehrung/#/skos-elemente?id=mappings). So tauchen beispielsweise Themen der Kirchengeschichte in vielen der o.g. Vokabulare auf, können aber bislang nicht bestandsübergreifend und harmonisiert gesucht werden.
* **Darstellung der Relationen:** Auch innerhalb der einzelnen Systematiken werden interne Relationen nur unzureichend abgebildet (vgl. https://dini-ag-kim.github.io/skos-einfuehrung/#/skos-elemente?id=relationen), womit den Nutzer*innen der Zugang zu den Informationen erschwert wird. So sind beispielsweise für eine erschöpfende Recherche zu Themen der Kirchengeschichte mehrere assoziierte Systemstellen mit territorialer Zuordnung (Deutschland, Italien, Preußen etc.) relevant, die in keiner direkten hierarchischen Beziehung zueinander stehen. Diese Relationen werden bislang nicht abgebildet.
* **Zusätzliche Suchbegriffe:** Für eine bessere Auffindbarkeit und Indexierung können zusätzliche Begriffe mittels skos:hiddenLabel ergänzt werden, die nicht in der Systematik angezeigt werden.
* **Mangelnde Unterstützung neuer DH-Projekte:** Zukünftige Projekte der Digital Humanities am Institut sollen das bislang verwendete Vokabular einfacher in ihre Arbeit integrieren, nachnutzen, pflegen und erweitern können, wozu bislang ein SKOS-Prozess am DHI fehlt und mit Hilfe der Bibliothek zu etablieren ist. Nicht zuletzt wird damit auch die Einheitlichkeit gefördert, ein zutiefst bibliothekarisches Anliegen.
* **Internationalität:** Das Institut arbeitet im internationalen Kontext, was SKOS durch die Mehrsprachigkeit seiner Vokabulare gemäß RDF/Turtle durch die Anhänge @de, @it etc. ideal unterstützt.
* **Services für die Fachcommunity:** Fachcommunites sollen insgesamt besser unterstützt werden, z.B. durch neue Ansätze wie sie aktuell am hbz im Microbloggingbereich erprobt werden (Stichwort Activity Pub, vgl. [ProLibris: Mitteilungsblatt 3/23, S.111](https://www.bibliotheken-nrw.de/wp-content/uploads/2023-3-_ProLibris-web-DS.pdf)). Für solche webbasierte Subskriptions- und Benachrichtigungssysteme erscheint die Kodierung und Publikation nach SKOS ein wichtiger erster Schritt, um die grundsätzliche Anschlussfähigkeit des DHI an entsprechende Entwicklungen zu gewährleisten.

Weder in der römischen Bibliothek noch in unserer MALIS-Projektgruppe besteht bei Projektstart ein Vorwissen zu RDF und SKOS. Im Verlauf der Vorgespräche für das kleine IT-Projekt gewinnt aber der Bedarf entsprechender Bibliotheksdienstleistungen klar an Kontur, insbesondere im Dialog mit der Digital Humanities-Abteilung. Als Projektidee soll anhand des bibliothekarisch wichtigsten und ältesten Vokabulars des DHI (1.1.1 Historische Bibliothek) mit dem größten repräsentierten Medienbestand prototypisch ein Verfahren zur semiautomatischen SKOS-Transformation  entwickelt, beispielhaft erprobt und nach Abschluss übergeben werden. Von Vorteil ist dabei, dass es sich um ein für das DHI Rom typisches und zweisprachiges Klassifikationssystem handelt. In dem transformierten Vokabular werden neben den SKOS-Grundelementen (vgl. 3.1) auf der Ebene der TopConcepts beispielhaft redaktionelle Eingriffe mit weiteren SKOS-Elementen vorgenommen (vgl. Abschnitt 3.4). In der späteren Betriebspraxis liegt in der Fortführung dieser redaktionellen Bearbeitung eine Aufgabe für den römischen Fachreferenten.

Die Vokabulare 1.1.2 bis 1.1.4 sowie 1.2.5 können nach Abschluss des Projekts und Übergabe des Verfahrens nach demselben Muster bearbeitet werden, da sich die PDF-Ausgangsdateien ähneln. Für 2025 ist ein Web-Relaunch der "Informazioni bibliografici" (1.2.5) in Planung, die Bibliothek kann mit dieser Maßnahme einen wichtigen Beitrag leisten. Auch wäre im weiteren Fortschritt ein Mapping zwischen den aufbereiteten SKOS-Vokabularen des Instituts möglich und im Sinne der o.g. Analyse angeraten.

Für die genannten Digital Humanties-Vokabulare 1.2.1 - 1.2.4 wären einige Teilschritte wiederverwendbar. Da die Vokabulare bereits in XML-Formaten vorliegen und auch in Teilen bereits Verküpfungen zu externen Normvokabularen enthalten, müssten Transformation und Bearbeitung insgesamt aber noch angepasst und weiter optimiert werden. Ingesamt fügt sich ein solches Vorhaben gut in den Rahmen eines am Institut entstehenden Digital Humanities Labs ein, in dem die Bibliothek als Partner der Wissenschaft u.a. maßgeschneiderte Metadatenservices übernehmen soll.

[↑ zurück zur Übersicht](#0)
<a name="2"></a>
## 2. Organisation der Zusammenarbeit

Nach dem ersten Projektentwurf wurde für die weitere Zusammenarbeit auf der Basis der Einführungsmaterialien der Fork des SkoHub-Docker-Vocabs-Repository eingerichtet (https://github.com/jang-rome/skohub-docker-vocabs) und um ein vierspaltiges Kanban Board ergänzt (https://github.com/users/jang-rome/projects/4). Bei Bedarf wurden kurzfristige Zoom- Sitzungen vereinbart und protokolliert (vgl. unten: Kanban und HedgeDoc in Kombination). 

Ausgesprochen hilfreich war bei der Einrichtung des Repository das zur Verfügung gestellte Demo-Video, das nur auf Codeberg verlinkt war: https://codeberg.org/acka47/malis/src/branch/main/pages/praxisprojekt.md.

Die oftmals bemängelte begrenzte Komplexität des Kanban Boards stellte für das Projekt kein Problem dar. Das Board erwies sich als angemessenes und einfach zu verwaltendes Arbeitsinstrument für a) die variable Aufteilung des Vorhabens in Teilaufgaben, b) die einfache Übernahme offener Teilaufgaben, c) die Visualisierung und Kurz-Dokumentation des Arbeitsstands bei unterschiedlichen Arbeitsrhythmen und d) die laufende Pflege von Kurznotizen, die auch in den Arbeitsbericht einfließen konnten. Die letzten beiden Punkte bringen nach unserer Meinung eine höhere Übersichtlichkeit als Chats oder Mailkommunikation. Als besonders hilfreich erwies sich im Projektverlauf die Spalte „QA“ zur unkomplizierten Dokumentation von Problemen und Rückfragen – so z.B. der Fall bei zunächst ungelösten Fragen zur SKOS-Validierung (3.1) und zu SKOS-Relationsfehlern (Hauptgruppe J, vgl. 3.4). Dringender Klärungs- oder Handlungsbedarf ließ sich so auf einen Blick erkennen.

Da wir in der Zeitplanung und in den Milestones im kleinen Projekt mangels Erfahrung mit SKOS flexibel und mit gewissen Toleranzen agieren wollten, hat sich Kanban im Rückblick gegenüber einem klassischen Gantt Chart bewährt.

Doch das Board hatte auch Grenzen: Um Ergebnisse von Zoom Sitzungen ausführlicher zu protokollieren und laufend einen Abeitsbericht zu erzeugen, wurde das Kanban Board durch den Markdown-Editor HegdeDoc flankiert. Diese Echtzeit-Protokolle und Kanban bildeten in ihrer Gesamtheit den Projektstand immer ausreichend ab. 

[↑ zurück zur Übersicht](#0)
<a name="3"></a>
## 3. Stufenweise Umsetzung der SKOS-Transformation
<a name="3.1"></a>
### 3.1 Erarbeitung eines validierten SKOS-Grundgerüsts

Auf der Basis der [SKOS-Einführung](https://dini-ag-kim.github.io/skos-einfuehrung/#/) und verschiedener Praxisbeispiele wie der
[Hochschulfächersystematik nach Destatis](https://github.com/dini-ag-kim/hochschulfaechersystematik) wurde ein SKOS-Minimalgerüst für die vorliegende Systematik definiert und in den ersten drei Hauptgruppen A-C erprobt und validiert.


```
@prefix syshist: <http://dhi-roma.it/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .

syshist: a skos:ConceptScheme ;
    dct:title "Klassifikation DHI Rom Historische Bibliothek - (Beta, per Skript generierte Rohdaten)"@de, "Divisone del catalogo sistematico del DHI Rom Biblioteca Storica - (Beta, dati grezzi)"@it ;
    dct:description "Semi-automatisierte SKOS-Transformation des seit 1910 verwendeten Klassifikationsschemas der Historischen Bibliothek des DHI Rom."@de, "Trasformazione automatica in SKOS dello schema di classificazione utilizzato dalla Biblioteca storica del DHI di Roma dal 1910."@it ;
    dct:creator "Jan-Peter Grünewälder", "Jonas Balzukat", "Regina Sofia Margarete Albrecht" ;
    dct:license <https://creativecommons.org/public-domain/cc0/> ;
    skos:hasTopConcept syshist:A, syshist:B, syshist:C .

   
syshist:A a skos:Concept ;
    skos:prefLabel "Allgemeines"@de, "In generale"@it ;
    skos:notation "A" ;
    skos:topConceptOf syshist: ;
    skos:narrower syshist:Aa, syshist:Ab, syshist:Ac, syshist:Ae .

syshist:Aa a skos:Concept ;
    skos:prefLabel "Enzyklopädien, allgemeine und biographische Lexika"@de, "Enciclopedie, lessici generäli e biografici"@it ;
    skos:notation "Aa" ;
    skos:broader <A> ;
    skos:inScheme syshist: .
```

Zentrale Elemente zur Kodierung und SkoHub-Darstellung werden an diesen Auszug bereits deutlich: Neben den Namensraum-Präfixen und der Definition des Gesamtvokabulars (skos:ConceptScheme) werden beispielsweise die einzelnen Systemstellen (Konzepte) mit einem Identifier und Hauptbezeichnung versehen, ihre Hierarchien u.a. mit dem Begriffspaar skos:narrower und skos:broader abgebildet. Da noch keine Concept URIs vorlagen (vgl. Arbeitsschritt 3.3), wurde dabei zunächst mit einem provisorischen Präfix syshist: (für "Systematik Historische Bibliothek") gearbeitet, d.h. die Identifier wurden erst in einem späteren Bearbeitungsschritt durch die persistenten PURL-URIs ersetzt.

Zwei wesentliche Erkenntnisse ergaben sich bei diesem Bearbeitungsschritt:

* **Validierung:** Schnell wurde uns deutlich, wie wichtig für die Validierung die Wahl eines geeigneten Tools ist. Trotz erfolgreicher Validierung im Turtle Web Editor (Meldung "Congrats! Your syntax is correct") schlug die Validierung bei der SkoHub Generierung in GitHub zu unserer Überraschung anfangs mehrfach fehl (vgl. Protokoll der Workflow-Runs auf GitHub https://github.com/jang-rome/skohub-docker-vocabs/actions). Wir ergänzten daher im Projektverlauf das SKOS Testing Tool, das abweichende und präzisere Ergebnisse lieferte. Beide Tools führen unterschiedliche Arten von Überprüfungen durch: Der Turtle Web Editor konzentriert sich hauptsächlich auf die Überprüfung der Syntax (Basis TurtleValidator https://github.com/IDLabResearch/TurtleValidator). Das SKOS Testing Tool ist spezialisiert auf die Validierung von SKOS-Vokabularen anhand eines konfigurierbaren Regelsets (https://skos-play.sparna.fr/skos-testing-tool/) und führt spezifischere Tests durch, um sicherzustellen, dass unsere Dateien den SKOS-Standards entsprechen. So wurden z.B. Warnungen zur Nichtdokumentation von Konzepten, fehlende Language Codes und Hierarchiefehler durch das Testing Tool erkannt, die dem Turtle Web Editor verborgen blieben.
* **Hierarchien:** Auffällig war in diesem Bearbeitungsschritt, dass die SkoHub Darstellung der Hierarchie auch ohne skos:broader noch korrekt funktionieren würde, also die Angabe einer Richtung ausreicht (vgl. auch https://dini-ag-kim.github.io/skos-einfuehrung/#/skos-kodierung?id=unterbegriffe). Trotzdem haben wir in der endgültigen TTL-Version skos:broader nach zwischenzeitlichen Tests wieder ergänzt.
  
[↑ zurück zur Übersicht](#0)

<a name="3.2"></a>
### 3.2 Erarbeitung eines Verfahrens zur semiautomatisierten Transformation
Dokumentation der Umwandlung einer DHI-Klassifikation in ein SKOS-Format

* **Ausgangspunkt und OCR-Digitalisierung**
Problematisch war, dass die Klassifikation 1.1.1 lediglich als gescanntes Image-PDF-Dokument verfügbar war. Um diese in ein bearbeitbares Format zu überführen, nutzten wir Adobe Acrobat für die Optical Character Recognition (OCR). Diese Technologie ermöglichte es uns, den Text aus dem PDF zu extrahieren, wobei wir im Anschluss den generierten Text manuell verfeinerten, um Digitalisierungsfehler zu korrigieren.

* **Sprachliche Aufbereitung**
Nach der Digitalisierung unterteilten wir die Systematik in zwei Sprachversionen: Deutsch und Italienisch. Diese Aufteilung war entscheidend, um eine klare Strukturierung und spätere Verarbeitung der Daten zu gewährleisten.

* **Übertragung in Excel**
Der nächste Schritt bestand darin, die strukturierten Daten sorgfältig in ein Excel-Dokument zu übertragen. Hierbei legten wir Wert darauf, Fehler zu korrigieren und die Daten strukturell aufzubereiten, um eine solide Grundlage für die folgenden Automatisierungsschritte zu schaffen.

* **Entwicklung einer Vorlage für die Automatisierung**
Um die Systematik effizient in ein SKOS-konformes Format zu überführen, erstellten wir eine spezifische Excel-Vorlage (https://github.com/jang-rome/skohub-docker-vocabs/blob/main/AutomatisiertesVokabular.xlsx). Diese Vorlage diente als Basis für das Python-Skript und beinhaltete vordefinierte Spalten, die den SKOS-Elementen wie prefLabel, notation und topConceptOf entsprachen.

* **Python-Programmierung im Jupyter Notebook**
Für die eigentliche Programmierarbeit wählten wir Jupyter Notebook als Entwicklungsumgebung. Diese Plattform ermöglichte es uns, Python-Code in einer interaktiven und übersichtlichen Weise zu schreiben und auszuführen. Durch den Einsatz von Jupyter Notebook konnten wir den Code Schritt für Schritt entwickeln und testen, was besonders bei der Fehlersuche und -behebung (Trial-and-Error-Methodik) hilfreich war.

* **Generierung eines RDF/Turtle-Dokuments**
Nach der erfolgreichen Entwicklung unseres Python-Skripts (vgl. [Anhang 5](#5-Anhang-Python-Skript-zur-semiautomatisierten-SKOS-Transformation)) konnten wir die Daten aus dem Excel-Dokument extrahieren und in das SKOS-Format transformieren. Dieser Prozess führte zur automatisierten Erstellung eines RDF/Turtle-Dokuments. Anfänglich lag der Fokus auf der Abbildung der ersten vier Systemstellen (A, B, C und D). Nachdem wir die Funktionalität und Genauigkeit unseres Skripts validiert hatten, erweiterten wir den Prozess, um das gesamte Vokabular der Klassifikation automatisiert in SKOS-Code zu überführen. Diese Automatisierung war ein hilfreicher Schritt, da sie es uns ermöglichte, die umfangreiche Systematik effizient und (weitestgehend) fehlerfrei in ein maschinenlesbares Format zu konvertieren.

[↑ zurück zur Übersicht](#0)

<a name="3.3"></a>
### 3.3 Einrichtung langfristig verfügbarer URI (Purl.org)

Für das Projekt werden "persistent uniform resource locator" (PURL) verwendet. Die Domain wurde so gewählt, dass weitere Subdomains für die nächsten Projektstufen ergänzt werden können, also neben dem aktuellen **/dhi-library/syshist** (https://purl.archive.org/domain_search?q=dhi-library) in Zukunft auch **/dhi-library/sysmusic** für die Musik-Klassifikation oder **/dhi-library/sysmanacorda** für die Manacorda-Klassifikation.

Die Konfiguration des Redirects nach der [Anleitung](https://github.com/skohub-io/swib20-workshop/blob/main/resources/publish-vocab.md#step-6-set-up-redirect-for-persistent-identifiers) scheiterte zunächst. Letztlich wurden manuelle Redirects für alle skos:Concepts eingerichtet, um die Funktionalität zeitnah zu gewährleisten. Die persistenten Konzept-URIs konnten so im nächsten Schritt bei der Beschreibung einer Ressource verwendet werden (z.B. https://purl.org/dhi-library/syshist/E) und "@base <https://purl.org/dhi-library/syshist/>" im TTL-File ergänzt werden. 
[↑ zurück zur Übersicht](#0)

<a name="3.4"></a>
### 3.4 Finale Bearbeitung Gesamtvokabular und SkoHub-Publikation

In den Schritten 3.1 und 3.2 lag der Fokus auf der Transformation der Systematik in eine Basis-SKOS-Kodierung. Vorrangiges Ziel des letzten Arbeitsschritts war die exemplarische Anreicherung mit weiteren SKOS-Elementen, um den Mehrwert zu illustrieren. Dazu wurden insbesondere auf der Ebene der TopConcepts folgende Elemente ergänzt:

**1. Optimierte Dokumentation und Pflege:**
* **skos:definition** - Kurzdefinitionen der Begriffe
* **skos:example** - Anwendungsbeispiele für die Verwendung der Systemstellen
* **skos:historyNote** - Die Klassifiktion wurde 1911 entwickelt, einige Systemstellen haben historisch bedingte Änderungen in der Bedeutung des Begriffs erfahren, die hier dokumentiert werden.
* **skos:scopeNote** - Im Laufe der Zeit wurden Systemstellen zu uneinheitlich durch die Fachreferent*innen vergeben. Es werden an dieser Stelle deshalb Regeln zur Anwendung gegeben, so z.B. die vorrangige Vergabe territorialer Systemstellen bei Werken mit lokalgeschichtlichen Schwerpunkten festgelegt.

**2. Verbesserte Suchbarkeit:**
* **skos:hiddenLabel** 	- Angereichertes Vokabular, hier wird eine weitere Bezeichnung für Indexierung und Suche vergeben, die in der Anzeige ausgeblendet wird.


**3. Optimierung der Mehrsprachigkeit**
* **@de / @it** - Bei der Bearbeitung und Validierung stellte sich heraus, dass neuere Systemstellen nicht konsequent zweisprachig geführt worden sind. Fehlende bzw. fehlerhafte Übersetzungen wurden ergänzt und korrigiert, so dass das Vokabular nun durchgängig Deutsch-Italienisch vorliegt.

**4. Erweiterte Erfassung der Relationen**
* **skos:related** - Verwandte (non-hierarchische) Systemstellen wurden analysiert und verlinkt.

Bei der Arbeit mit skos:related kam es in der SkoHub-Publikation wiederholt zu Sortierungsfehlern. So sortierten in der Darstellung z.B. die Systemstellen "Je" und "Jf" vor "Ja". Verursacht wurde dieser Fehler offensichtlich durch skos:related-Verlinkungen von Elementen der Unterebenen auf TopConcepts. Ein Widerspruch zu den [W3C-Empfehlungen](https://www.w3.org/TR/2009/REC-skos-reference-20090818/#semantic-relations) (Stichwort "non consistent") war für uns nicht erkennbar, auch wurden keine Validierungsfehler ausgegeben.  Wir haben die betroffenen Beziehungen aber nachträglich entfernt, um die Sortierungsfehler zuverlässig zu beseitigen.
[↑ zurück zur Übersicht](#0)

<a name="4"></a>
## 4. Ausblick

Bei der Systematik der Historischen Bibliothek handelte es sich wie aufgezeigt nur um einen ersten Use Case, der jetzt übergeben wird. In den in Abschnitt 1.3 skizzierten zukünftigen Projektschritten wird es darum gehen, das weitere Potential der SKOS-Kodierung und SkoHub-Publikation auszuspielen. Dazu wird entscheidend sein, die zusätzlichen Instituts-Vokabulare mit der aufgezeigten Methode normgerecht und maschinenlesbar zu kodieren, auf dem offiziellen [DHI-GitHub-Repo ](https://github.com/DHI-Roma)als skohub-docker-vocabs-Fork zu publizieren und diese *untereinander* - aber auch mit *externen* (Norm-)Vokabularen - zu matchen. Letzteres machen die am DHI angesiedelten Digital Humanities Projekte bereits in Ansätzen vor, allerdings noch ohne SKOS-Kodierung und Publikation. SKOS bietet dazu zahlreiche [Mapping-Elemente](https://dini-ag-kim.github.io/skos-einfuehrung/#/skos-elemente?id=mappings) wie skos:closeMatch und skos:exactMatch, die im vorliegenden Use Case noch ungenutzt bleiben. Basierend auf den gesammelten, äußerst wertvollen Erfahrungen des kleinen Projekts sollen diese Aufgaben nun von der DHI-Bibliothek in Angriff genommen werden. 



[↑ zurück zur Übersicht](#0)
<a name="5"></a>
## 5. Anhang: Python-Skript zur semiautomatisierten SKOS-Transformation

````=
import pandas as pd

# Dateipfad der bereitgestellten Excel-Datei
excel_file_path = 'C:\\Users\\Jonas\\Downloads\\AutomatisiertesVokabular.xlsx'

# Einlesen der Excel-Datei
df_concepts = pd.read_excel(excel_file_path, sheet_name='Konzepte')
df_schema_metadata = pd.read_excel(excel_file_path, sheet_name='Konzeptschema-Metadaten')

# Metadaten für dct:title und dct:description kombinieren
title_de = df_schema_metadata.loc[0, 'dct:title-de']
title_it = df_schema_metadata.loc[0, 'dct:title-it']
description_de = df_schema_metadata.loc[0, 'dct:description-de']
description_it = df_schema_metadata.loc[0, 'dct:description-it']

# Erstellen des RDF/Turtle-Strings mit kombinierten Metadaten
turtle_string = f"""
@prefix syshist: <http://dhi-roma.it/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix dct: <http://purl.org/dc/terms/> .

syshist: a skos:ConceptScheme ;
    dct:title "{title_de}"@de, "{title_it}"@it ;
    dct:description "{description_de}"@de, "{description_it}"@it ;
"""

# Hinzufügen der restlichen Metadaten
creator = df_schema_metadata.loc[0, 'dct:creator']
issued = df_schema_metadata.loc[0, 'dct:issued']
license = df_schema_metadata.loc[0, 'dct:license']
turtle_string += f'    dct:creator <{creator}> ;\n'
turtle_string += f'    dct:issued "{issued}" ;\n'
turtle_string += f'    dct:license <{license}> ;\n'

# Hinzufügen der Top-Konzepte
top_concepts = df_schema_metadata.loc[0, 'skos:hasTopConcept'].split(", ")
if top_concepts:
    turtle_string += '    skos:hasTopConcept ' + ', '.join(f'syshist:{tc.replace("syshist:", "")}' for tc in top_concepts) + ' ;\n'
turtle_string = turtle_string.strip().rstrip(';') + '.\n\n'

# Konzepte hinzufügen und überprüfen, ob Narrower-Beziehungen vorhanden sind
for _, concept_row in df_concepts.iterrows():
    code = concept_row['Code']
    de_label = concept_row['Deutscher Titel']
    it_label = concept_row['Italienischer Titel']
    notation = concept_row['Notation']
    top_concept_of = concept_row['Top Concept Of']
    in_scheme = concept_row['In Scheme']

    turtle_string += f'syshist:{code} a skos:Concept ;\n'
    turtle_string += f'    skos:prefLabel "{de_label}"@de, "{it_label}"@it ;\n'
    turtle_string += f'    skos:notation "{notation}" ;\n'
    if top_concept_of == 'syshist:':
        turtle_string += f'    skos:topConceptOf syshist: ;\n'
    elif pd.notna(in_scheme):
        turtle_string += f'    skos:inScheme syshist: ;\n'

    # Narrower Konzepte für Oberkategorien hinzufügen
    narrower_concepts = df_concepts[df_concepts['Top Concept Of'] == code]['Notation'].tolist()
    if narrower_concepts:
        turtle_string += f'    skos:narrower ' + ', '.join(f'syshist:{n}' for n in narrower_concepts) + ' ;\n'

    turtle_string = turtle_string.strip().rstrip(';') + '.\n\n'

# Turtle-String in Datei schreiben
turtle_file_path = 'C:\\Users\\Jonas\\Downloads\\Automatisierungsdatei.ttl'
with open(turtle_file_path, 'w', encoding='utf-8') as f:
    f.write(turtle_string)

print(turtle_file_path)



