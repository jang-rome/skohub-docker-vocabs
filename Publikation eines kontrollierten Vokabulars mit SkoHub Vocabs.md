
# Publikation eines kontrollierten Vokabulars mit SkoHub Vocabs
Projektbericht Modul MALIS 23.2 IT 2
Dozent: Adrian Pohl

**Arbeitsgruppe:** 
Regina Sofia Margarete Albrecht (Matrikelnummer: 11188249 ),
Email: Regina_sofia_margarete.albrecht@smail.th-koeln.de
Jonas Balzukat (Matrikelnummer: 11096598 ),
Email: Jonas.Balzukat1@smail.th-koeln.de
Jan-Peter Grünewälder  (Einzelmodulbucher)
Email: grunewalder@dhi-roma.it

## 1. Auswahl des kontrollierten Vokabulars und Entwicklung einer Projektidee

Zu Beginn des Projekts wurde das am DHI Rom eingesetzte kontrollierte Vokabular identifiziert. Es erstreckt sich zum einen auf verschiedene bibliothekarische Klassifikationen und zum anderen auf Vokabular, das seit 2004 im Kontext der Digital Humanities entstanden ist.

### 1.1 Bibliothek
Die Bibliothek vereint zwei große wissenschaftliche Bestände der Musik- und Geschichtswissenschaft mit insgesamt ca. 300.000 Medieneinheiten. Sie werden seit 2017 organisatorisch zusammengeführt, sind aber aus historischen Gründen in zwei unterschiedlichen Fachsystematiken erschlossen und aufgestellt. Daneben integriert die Bibliothek zwei umfangreiche Spezialsammlungen zur Geschichte des italienischen Faschismus (Privatbibliothek des Journalisten und Zeithistorikers Dulio Susmel) und zur italienischen Parteiengeschichte (Privatbibliothek des Historikers Gastone Manacorda) mit eigener systematischer Erschließung ihrer ehemaligen Eigentümer.


![](https://pad.gwdg.de/uploads/5e88e834-3311-44fb-9474-9f15beb0b8e3.png)


### 1.2 Digital Humanities und Institutspublikationen

Im Bereich der Digital Humanities und der Redaktionsarbeit werden fünf Vokabulare aus den digitalen Editionen und Projekten in die Betrachtung einbezogen:

![](https://pad.gwdg.de/uploads/ee42671b-b61e-4f11-b5fa-d49b394976c6.png)



### 1.3 Entwicklung der Projektidee

In der Analyse ergibt sich in Bezug auf die kontrollierten Vokabulare ein insgesamt unbefriedigendes Bild, d.h. das Potential kontrollierter Vokabulare wird am DHI nicht ausgeschöpft, was gerade unter den Gesichtspunkten der Sichtbarkeit und Zugänglichkeit der klassifikatorisch oder verbal erschlossenen (Daten-)Bestände ein Manko darstellt. Einige zentrale Punkte unserer Analyse in Auswahl: 

* Normierung: Keines der bibliothekarischen Vokabulare liegt maschinenlesbar und standardgerecht im Resource Description Framework (RDF) kodiert vor, zudem ist keines langfristig referenzierbar z.B. mittels PURL-URIs.
* Dokumentation: Für die Pflege und transparente Dokumentation der bibliothekarischen Vokabulare kommen keine digitalen Methoden zum Einsatz, es existieren im Wesentlichen nur gescannte PDF-Übersichten. SKOS bietet hier verschiedene relevante Dokumentations-Elemente wie skos:definition, skos:historyNote, skos:scopeNote etc. an (vgl. https://dini-ag-kim.github.io/skos-einfuehrung/#/skos-elemente?id=dokumentation).
* Verlinkung: Die Erschließung der Bibliotheksbestände (1.1.1 – 1.1.4) und der bibliographischen Informationsdienste (1.2.5) erfolgt bis dato ohne jegliche Verlinkung (z.B. SKOS-Mappings wie https://dini-ag-kim.github.io/skos-einfuehrung/#/skos-elemente?id=mappings). So tauchen beispielsweise Themen der Kirchengeschichte in vielen der o.g. Vokabulare auf, können aber bislang nicht bestandsübergreifend und harmonisiert gesucht werden.
* Darstellung der Relationen: Auch innerhalb der einzelnen Systematiken werden interne Relationen nur unzureichend abgebildet (vgl. https://dini-ag-kim.github.io/skos-einfuehrung/#/skos-elemente?id=relationen) und erschweren den Nutzer*innen den Zugang zu den Informationen. So sind beispielsweise für eine erschöpfende Recherche zu Themen der Kirchengeschichte mehrere assoziierte Systemstellen mit territorialer Zuordnung (Deutschland, Italien, Preußen etc.) relevant, die in keiner direkten hierarchischen Beziehung untereinander stehen. Diese Relationen werden bislang nicht abgebildet.
* Zusätzliche Suchbegriffe: Für bessere Auffindbarkeit und Indexierung können zusätzliche Begriffe mittels skos:hiddenLabel ergänzt werden, die nicht in der Systematik angezeigt werden.
* Mangelnde Unterstützung neuer DH-Projekte: Zukünftige Projekte der Digital Humanities am Institut sollen das bislang verwendete Vokabular einfach in ihre Arbeit integrieren, nachnutzen und erweitern können, wozu bislang ein SKOS-Prozess am DHI fehlt und zu etablieren ist. Letztlich wird damit auch die Einheitlichkeit gefördert.
* Internationalität: Das Institut arbeitet im internationalen Kontext, was SKOS durch die Mehrsprachigkeit seiner Vokabulare gemäß RDF/Turtle durch die Anhänge @de, @it etc. ideal unterstützt.
* Services für die Fachcommunity: Fachcommunites sollen insgesamt besser unterstützt werden, z.B. durch neue Ansätze wie sie aktuell am hbz im Microbloggingbereich erprobt werden (vgl. ProLibris: Mitteilungsblatt 3/23, S.111, https://www.bibliotheken-nrw.de/wp-content/uploads/2023-3-_ProLibris-web-DS.pdf ) Hier erscheint die Kodierung und Publikation nach SKOS ein wichtiger erster Schritt, um die grundsätzliche Anschlussfähigkeit des DHI an solche Entwicklungen zu gewährleisten.

Weder in der römischen Bibliothek noch in unserer MALIS-Projektgruppe besteht bei Projektstart ein Vorwissen zu RDF und SKOS. Im Verlauf der Vorgespräche für das kleine IT-Projekt gewinnt aber der Bedarf entsprechender Bibliotheksdienstleistungen klar an Kontur, insbesondere seitens der DH-Abteilung. Als Projektidee soll anhand des bibliothekarisch wichtigsten und ältesten Vokabulars des DHI (1.1.1 Historische Bibliothek) mit dem größten repräsentierten Medienbestand prototypisch ein Verfahren zur semiautomatischen SKOS-Transformation  entwickelt, beispielhaft erprobt und nach Abschluss übergeben werden. Von Vorteil ist dabei, dass es sich um ein für das DHI Rom typisches und zweisprachiges Klassifikationssystem handelt. In dem transformierten Vokabular werden neben den SKOS Grundelementen (vgl. 3.1) auf der Ebene der TopConcepts beispielhaft redaktionelle Eingriffe mit weiteren SKOS Elementen vorgenommen (vgl. Abschnitt 3.4). In der späteren Betriebspraxis liegt in der Fortführung dieser redaktionellen Bearbeitung eine Aufgabe für die römischen Fachreferenten.

Die Vokabulare 1.1.2 bis 1.1.4 sowie 1.2.5 können nach Abschluss des Projekts und Übergabe des Verfahrens nach demselben Muster bearbeitet werden, da sich die PDF-Ausgangsdaten ähneln. Da ein Web-Relaunch der "Informazioni bibliografici" in Planung ist, kann die Bibliothek hier einen wichtigen Beitrag leisten. Auch wäre im weiteren Fortschritt ein Mapping zwischen den aufbereiteten SKOS-Vokabularen des Instituts möglich und im Sinne der o.g. Analyse angeraten.

Für die genannten Digital Humanties-Vokabulare 1.2.1 - 1.2.4 wären einige Teilschritte wiederverwendbar. Da die Vokabulare bereits in XML-Formaten vorliegen und auch in Teilen bereits Verküpfungen zu externen Normvokabularen enthalten, müsssten Transformation und Bearbeitung insgesamt aber noch angepasst und weiter optimiert werden. Ingesamt fügt sich ein solches Vorhaben gut in den Rahmen eines am Institut entstehenden Digital Humanities Labs, in dem die Bibliothek als Partner der Wissenschaft u.a. maßgeschneiderte Metadatenservices übernehmen soll.



## 2. Organisation der Zusammenarbeit

Nach dem ersten Projektentwurf wurde für die weitere Zusammenarbeit auf der Basis der Einführungsmaterialien der Fork des SkoHub-Docker-Vocabs-Repository eingerichtet (https://github.com/jang-rome/skohub-docker-vocabs) und um ein vierspaltiges Kanban Board ergänzt (https://github.com/users/jang-rome/projects/4). Bei Bedarf wurden kurzfristige Zoom- Sitzungen vereinbart und protokolliert (vgl. unten: Kanban und HedgeDoc in Kombination). 

Ausgesprochen hilfreich war bei der Einrichtung des Repository das zur Verfügung gestellte Demo-Video, das nur auf Codeberg verlinkt war: https://codeberg.org/acka47/malis/src/branch/main/pages/praxisprojekt.md

Die oftmals bemängelte begrenzte Komplexität des Boards stellte für das Projekt kein Problem dar. Kanban erwies sich als angemessenes und einfach zu verwaltendes Arbeitsinstrument für a) die grundsätzliche Aufteilung von Teilaufgaben, b) die einfache Übernahme offener Teilaufgaben, c) die Visualisierung und Kurz-Dokumentation des Arbeitsstands bei unterschiedlichen Arbeitsrhythmen und d) die laufende Pflege von Kurznotizen, die auch in den Arbeitsbericht einfließen konnten und eine erhöhte Übersichtlichkeit im Vergleich zu Chats oder Mailkommunikation bieten. Als besonders wichtig erwies sich im Projektverlauf die Spalte „QA“ für Klärungsbedarf und Rückfragen, da bei unvorhergesehenen Problemen oder Entscheidungsbedarf Issues nicht einfach in die „Done“-Spalte verschoben werden konnten – so z.B. der Fall bei ungelösten Fragen zur SKOS-Validierung und Beseitigung von SKOS-Relationsfehlern (Hauptgruppe J). Da eine feste Zeitplanung und Milestones im kleinen Projekt eine untergeordnete Rolle spielten, hat sich Kanban im Rückblick gegenüber einem klassischen Gantt Chart also durchaus bewährt.

Um Ergebnisse von Zoom Sitzungen ausführlich zu protokollieren und laufend einen Abeitsbericht zu erzeugen, wurde das Kanban Board durch den Markdown-Editor HegdeDoc flankiert. Diese Echtzeit-Protokolle und Kanban bildeten in ihrer Gesamtheit den Projektstand immer ausreichend ab. 



## 3. Stufenweise Umsetzung der SKOS-Transformation
### 3.1 Erarbeitung eines SKOS-Grundgerüsts
### 3.2 Erarbeitung eines Verfahrens zur semiautomatisierten Transformation
Dokumentation der Umwandlung einer Klassifikationssystematik in ein SKOS-Format

* **Ausgangspunkt und Digitalisierung**
Unser Projekt begann mit einer Klassifikationssystematik der DHI, die lediglich als PDF-Dokument verfügbar war. Um diese in ein bearbeitbares Format zu überführen, nutzten wir Adobe Acrobat für die Optical Character Recognition (OCR). Diese Technologie ermöglichte es uns, den Text aus dem PDF zu extrahieren, wobei wir im Anschluss den generierten Text manuell verfeinerten, um Digitalisierungsfehler zu korrigieren.

* **Sprachliche Aufbereitung**
Nach der Digitalisierung unterteilten wir die Systematik in zwei Sprachversionen: Deutsch und Italienisch. Diese Aufteilung war entscheidend, um eine klare Strukturierung und spätere Verarbeitung der Daten zu gewährleisten.

* **Übertragung in Excel**
Der nächste Schritt bestand darin, die strukturierten Daten sorgfältig in ein Excel-Dokument zu übertragen. Hierbei legten wir Wert darauf, Fehler zu korrigieren und die Daten strukturell aufzubereiten, um eine solide Grundlage für die folgenden Automatisierungsschritte zu schaffen.

* **Entwicklung einer Vorlage für die Automatisierung**
Um die Systematik effizient in ein SKOS-konformes Format zu überführen, erstellten wir eine spezifische Excel-Vorlage (https://github.com/jang-rome/skohub-docker-vocabs/blob/f4ab74c88cd7d45a1d8a1c8cefc3781ee5b2ea52/Klassifikation_DHIRom_HistBibl_beta.xlsx). Diese Vorlage diente als Basis für das Python-Skript und beinhaltete vordefinierte Spalten, die den SKOS-Elementen wie prefLabel, notation und topConceptOf entsprachen.

* **Python-Programmierung im Jupyter Notebook**
Für die eigentliche Programmierarbeit wählten wir Jupyter Notebook als Entwicklungsumgebung. Diese Plattform ermöglichte es uns, Python-Code in einer interaktiven und übersichtlichen Weise zu schreiben und auszuführen. Durch den Einsatz von Jupyter Notebook konnten wir den Code Schritt für Schritt entwickeln und testen, was besonders bei der Fehlersuche und -behebung (Trial-and-Error-Methodik) hilfreich war.

* **Generierung eines RDF/Turtle-Dokuments**
Nach der erfolgreichen Entwicklung unseres Python-Skripts (vgl. [5. Anhang](#Pythion-Skript) konnten wir die Daten aus dem Excel-Dokument extrahieren und in das SKOS-Format transformieren. Dieser Prozess führte zur automatisierten Erstellung eines RDF/Turtle-Dokuments. Anfänglich lag der Fokus auf der Abbildung der ersten vier Systemstellen (A, B, C und D). Nachdem wir die Funktionalität und Genauigkeit unseres Skripts validiert hatten, erweiterten wir den Prozess, um das gesamte Vokabular der Klassifikation automatisiert in SKOS-Code zu überführen. Diese Automatisierung war ein hilfreicher Schritt, da sie es uns ermöglichte, die umfangreiche Systematik effizient und fehlerfrei in ein maschinenlesbares Format zu konvertieren.


### 3.3 Einrichtung langfristig verfügbarer URI (Purl.org)
### 3.4 Applikation auf Gesamtvokabular und SkoHub-Publikation

## 4. Ausblick
<a name="Python-Skript"></a>
## 5. Anhang: Python-Skript zur semiautomatisierten SKOS Transformation





````

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
turtle_file_path = 'C:\\Users\\Jonas\\Downloads\\Dieperfektedatei.ttl'
with open(turtle_file_path, 'w', encoding='utf-8') as f:
    f.write(turtle_string)

print("RDF/Turtle-String wurde erfolgreich generiert und in die Datei geschrieben.")



