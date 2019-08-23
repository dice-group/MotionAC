Erläuterungen zu den als OpenData bereitgestellten Daten des Aachener Verkehrsverbund
=====================================================================================
Fassung vom 10.08.2017.

Unter http://opendata.avv.de stehen verschiedene Daten zu den Verkehren im AVV bereit.

Derzeit sind Fahrplanrohdaten im HAFAS- sowie im GTFS-Format verfügbar. Es ist geplant, die Inhalte und verfügbaren Daten weiter auszubauen.

In den Ordnern \current_xxx finden Sie den jeweils aktuellen Datensatz mit feststehendem Dateinamen.

In den Ordnern \archive_xxx finden Sie aktuelle und ältere Datensätze. Das Erstellungsdatum ist im Dateinamen enthalten. Die Ordner werden von Zeit zu Zeit aufgeräumt.

Lizenz
======
Gemäß Beschluss des Unternehmensbeirat des AVV vom 06.09.2016 sind die Fahrplandaten der AVV-Linien als 'gemeinfrei' entsprechend CC0 lizensiert. 

Die Fahrwege der Busse sind auf Basis von Openstreetmap erstellt worden. Daher gilt hier "© OpenStreetMap-Mitwirkende" gemäß der Open Data Commons Open Database Lizenz (ODbL).

Haftungsausschluss
==================
Der bereitgestellte Datenbestand kann Fehler enthalten und/oder unvollständig und/oder nicht aktuell sein. Der AVV oder die AVV-Partnerverkehrsunternehmen übernehmen keine Haftung und leisten keinerlei Gewähr.

Der AVV behält sich das Recht vor, die Formate, Struktur und Inhalte der Daten jederzeit zu verändern oder den Service gänzlich einzustellen.

Datenumfang
===========
Der Datensatz enthält alle Buslinien der AVV-Busunternehmen. (Ausnahme: Arriva Niederlande. Diese Daten sind bis zur vollständigen Integration über das niederländische Opendata-Portal verfügbar).

Zudem sind alle Züge aller Linien des Nahverkehrs enthalten, die das Gebiet des AVV berühren. Da bei Import und Aufbereitung ein gewisser Zeitverzug entsteht, können ggf. andere Quellen aktueller sein.

Die Fahrplandaten haben nicht den Anspruch, für die Vergangenheit vollständige oder korrekte Auskünfte zu liefern. Es sind nicht unbedingt alle abgelaufenen Quelldaten der Verkehrsunternehmen enthalten.

Formate
=======
Die Fahrplandaten stehen in den nachfolgenden Formaten zur Verfügung:
- AVV_HAFAS_520: 
Inkl. SPNV in der Rohdatenversion 5.20 mit Realgraph. 7-stellige Haltestellennummern.
Es wird keine gemeinsame FPLAN, sondern einzelne *.lin-Dateien geliefert. Ggf. können nicht gewünschte Linien vor dem Import herausgelöscht werden bzw. beim Import ignoriert werden.

- AVV_HAFAS_540:
Inkl. SPNV in der Rohdatenversion 5.40 mit Realgraph. 9-stellige Haltestellennummern.
Es wird keine gemeinsame FPLAN, sondern einzelne *.lin-Dateien geliefert. Ggf. können nicht gewünschte Linien vor dem Import herausgelöscht werden bzw. beim Import ignoriert werden.

- AVV_GTFS_mit_SPNV:
Inkl. aller Linien des Nahverkehrs, die das Verbundgebiet des AVV berühren.

- AVV_GTFS_ohne_SPNV:
Enthält nur die Daten der Busunternehmen.

- Haltestellen:
Enthält alle Haltestellen im AVV-Verbundgebiet (AVV_haltestellen.csv) sowie alle untergeordneten Masten (AVV_masten.csv). Es sind nur Haltestellen in der StädteRegion Aachen, dem Kreis Düren und den Kreis Heinsberg enthalten. Die Koordinaten sind im Format Gauß-Krüger 2 (EPSG:31466) gepflegt.
Da es sich bei den Haltestellendaten um "Ewigkeitsdaten" handelt, sind auch nicht mehr bediente, historische Haltestellen enthalten. In den HAFAS und GTFS-Daten sind hingegen nur die aktuell bedienten Haltestellen verfügbar.
Die Haltestellen sind stets einer Kommune zugeordnet, auch wenn sich die Masten in mehreren Kommunen befinden (z.B. Aachen/Herzogenrath Berensberg).

AVV_Haltestellen.csv: Entspricht der obersten Haltestellenebene
AVV_Masten.csv: Entspricht den physikalischen Masten

Haltestellen_Nachbarn.csv: Enthält die Umschlüsselungen zu den Nachbarlieferanten des AVV.
Hinweis: Die Nummern der TEC wurden vom AVV vergeben. In deren Daten sind nur Kürzel wie "LVAbuss2" enthalten.
Für die niederländischen Haltestellen wurde die Nummern des Lieferanten 9292ov ('OV') verwendet.

Ggf. könnte sich die Struktur der Dateien noch verändern.

API
===
Alternativ kann auch auf die API des AVV-Fahrgastinformationssystems genutzt werden. Dabei handelt es sich um die HAFAS-ReST-Schnittstelle. Die API kann als OpenService genutzt werden. Die Zugangsdaten zur API erhalten Sie nach Abschluss einer Nutzungsvereinbarung.

Hinweise zu den GTFS-Daten
==========================
Die Verkehrsmittel werden als "route_type" entsprechend des TPEG-Standards codiert. Dazu siehe auch
https://developers.google.com/transit/gtfs/reference/extended-route-types

106	Regional Rail Service	(RB, RE, DPN)
109	Suburban Railway	(S-Bahn)
704	Local Bus Service	(BUS, NFB)
713	School and Public Service Bus (BUS, NFB). Diese Fahrten haben in der AVV-Fahrplanauskunft die Fußnote "Verstärkerfahrt. Kann jederzeit ausfallen. Bus ist in der Regel als Linie 'V' beschildert."
714	Rail Replacement Bus Service (SEV)
715	Demand and Response Bus Service (anrufpflichtige Verkehre: ALT, Rufbus, Multibus, Netliner)

Rufnummern und Hinweise für Anruf-Verkehre:
===========================================
Bitte übernehmen Sie die anrufpflichtigen Fahrten nur dann, wenn Sie sicherstellen können, dass auch die Rufnummern mit ausgeben werden können. Ansonsten entsteht hier keine für den Fahrgast wirklich nutzbare Information.
Nutzen Sie gegebenenfalls den ebenfalls verfügbaren HAFAS-Datensatz.

Bei Multibus und Netliner handelt es sich um Verkehre, die ein größeres Gebiet ohne festen Fahrplan bedienen. Der Fahrplan ist hier nur eine modellhafte Darstellung und kann bei der Buchung deutlich abweichen.

2ALT, 6ALT, 12ALT, 15ALT, 17ALT, 26ALT, 27ALT, 30ALT, 37ALT, 46ALT, 48ALT, 55ALT, 57ALT, 74ALT, 77ALT, EW2ALT, EW4ALT, EW6ALT, WÜ1:
Anmeldung 30 Minuten vor Abfahrt Tel.: 02 41/4 01 39 99.

59ALT, HZ1ALT:
Anmeldung 30 Minuten vor Abfahrt Tel. 02 41/ 1 82 00 - 0.

223, 294:
Anmeldung (6 bis 20 Uhr) 30 Min. vor Abfahrt Tel.: 0 24 61/34 54 44.

261:
Anmeldung (8 bis 19:20 Uhr) 30 Min. vor Abfahrt Tel.: 0 24 09/70 111 90.

AL3ALT:
Anmeldung 30 Minuten vor Abfahrt Tel. 01 73/2 52 10 41.

HZ3RUF:
Anmeldung 30 Minuten vor Fahrtantritt unter Tel. 01 73/2 52 10 21.

RUFBUS C, RUFBUS F, RUFBUS H:
Anmeldung 30 Minuten vor Abfahrt Tel. 0 24 21/20 00.

Multibus (Linien MBxxx):
Anmeldung 60 Minuten vor Abfahrt Tel.: 0 24 31/88 66 88.

Netliner (Linien Netxx):
Anmeldung 30 Minuten vor Abfahrt Tel: 02 41/16 88 33 22 oder netliner.aseag.de. Die tatsächlichen Fahrzeiten erhalten Sie nach Buchung.

Herausgeber
===========
AACHENER VERKEHRSVERBUND GMBH
Neuköllner Straße 1
52068 Aachen
AVV-Linien 23, 30 und 43
Haltestelle ASEAG
Internet: www.avv.de
eMail: info@avv.de
----------------------------------------------------
Aufsichtsratsvorsitzender: Wilhelm Paffen
Geschäftsführer:
Hans-Peter Geulen
Dipl.-Ing. (FH) Heiko Sedlaczek
---------------------------------------------------
Registergericht Aachen, 
Handelsregister Abt. B Nr. 5952
USt-Id-Nr.: DE 169 963 856
Steuernummer: 201 59403252

Fragen
======
Bei Unklarheiten kann nur in ganz geringem Umfang und ohne Priorität ein Support geleistet werden. Wir bitten um Verständnis.
