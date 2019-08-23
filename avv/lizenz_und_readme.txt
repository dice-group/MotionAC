Erl�uterungen zu den als OpenData bereitgestellten Daten des Aachener Verkehrsverbund
=====================================================================================
Fassung vom 10.08.2017.

Unter http://opendata.avv.de stehen verschiedene Daten zu den Verkehren im AVV bereit.

Derzeit sind Fahrplanrohdaten im HAFAS- sowie im GTFS-Format verf�gbar. Es ist geplant, die Inhalte und verf�gbaren Daten weiter auszubauen.

In den Ordnern \current_xxx finden Sie den jeweils aktuellen Datensatz mit feststehendem Dateinamen.

In den Ordnern \archive_xxx finden Sie aktuelle und �ltere Datens�tze. Das Erstellungsdatum ist im Dateinamen enthalten. Die Ordner werden von Zeit zu Zeit aufger�umt.

Lizenz
======
Gem�� Beschluss des Unternehmensbeirat des AVV vom 06.09.2016 sind die Fahrplandaten der AVV-Linien als 'gemeinfrei' entsprechend CC0 lizensiert. 

Die Fahrwege der Busse sind auf Basis von Openstreetmap erstellt worden. Daher gilt hier "� OpenStreetMap-Mitwirkende" gem�� der Open Data Commons Open Database Lizenz (ODbL).

Haftungsausschluss
==================
Der bereitgestellte Datenbestand kann Fehler enthalten und/oder unvollst�ndig und/oder nicht aktuell sein. Der AVV oder die AVV-Partnerverkehrsunternehmen �bernehmen keine Haftung und leisten keinerlei Gew�hr.

Der AVV beh�lt sich das Recht vor, die Formate, Struktur und Inhalte der Daten jederzeit zu ver�ndern oder den Service g�nzlich einzustellen.

Datenumfang
===========
Der Datensatz enth�lt alle Buslinien der AVV-Busunternehmen. (Ausnahme: Arriva Niederlande. Diese Daten sind bis zur vollst�ndigen Integration �ber das niederl�ndische Opendata-Portal verf�gbar).

Zudem sind alle Z�ge aller Linien des Nahverkehrs enthalten, die das Gebiet des AVV ber�hren. Da bei Import und Aufbereitung ein gewisser Zeitverzug entsteht, k�nnen ggf. andere Quellen aktueller sein.

Die Fahrplandaten haben nicht den Anspruch, f�r die Vergangenheit vollst�ndige oder korrekte Ausk�nfte zu liefern. Es sind nicht unbedingt alle abgelaufenen Quelldaten der Verkehrsunternehmen enthalten.

Formate
=======
Die Fahrplandaten stehen in den nachfolgenden Formaten zur Verf�gung:
- AVV_HAFAS_520: 
Inkl. SPNV in der Rohdatenversion 5.20 mit Realgraph. 7-stellige Haltestellennummern.
Es wird keine gemeinsame FPLAN, sondern einzelne *.lin-Dateien geliefert. Ggf. k�nnen nicht gew�nschte Linien vor dem Import herausgel�scht werden bzw. beim Import ignoriert werden.

- AVV_HAFAS_540:
Inkl. SPNV in der Rohdatenversion 5.40 mit Realgraph. 9-stellige Haltestellennummern.
Es wird keine gemeinsame FPLAN, sondern einzelne *.lin-Dateien geliefert. Ggf. k�nnen nicht gew�nschte Linien vor dem Import herausgel�scht werden bzw. beim Import ignoriert werden.

- AVV_GTFS_mit_SPNV:
Inkl. aller Linien des Nahverkehrs, die das Verbundgebiet des AVV ber�hren.

- AVV_GTFS_ohne_SPNV:
Enth�lt nur die Daten der Busunternehmen.

- Haltestellen:
Enth�lt alle Haltestellen im AVV-Verbundgebiet (AVV_haltestellen.csv) sowie alle untergeordneten Masten (AVV_masten.csv). Es sind nur Haltestellen in der St�dteRegion Aachen, dem Kreis D�ren und den Kreis Heinsberg enthalten. Die Koordinaten sind im Format Gau�-Kr�ger 2 (EPSG:31466) gepflegt.
Da es sich bei den Haltestellendaten um "Ewigkeitsdaten" handelt, sind auch nicht mehr bediente, historische Haltestellen enthalten. In den HAFAS und GTFS-Daten sind hingegen nur die aktuell bedienten Haltestellen verf�gbar.
Die Haltestellen sind stets einer Kommune zugeordnet, auch wenn sich die Masten in mehreren Kommunen befinden (z.B. Aachen/Herzogenrath Berensberg).

AVV_Haltestellen.csv: Entspricht der obersten Haltestellenebene
AVV_Masten.csv: Entspricht den physikalischen Masten

Haltestellen_Nachbarn.csv: Enth�lt die Umschl�sselungen zu den Nachbarlieferanten des AVV.
Hinweis: Die Nummern der TEC wurden vom AVV vergeben. In deren Daten sind nur K�rzel wie "LVAbuss2" enthalten.
F�r die niederl�ndischen Haltestellen wurde die Nummern des Lieferanten 9292ov ('OV') verwendet.

Ggf. k�nnte sich die Struktur der Dateien noch ver�ndern.

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
713	School and Public Service Bus (BUS, NFB). Diese Fahrten haben in der AVV-Fahrplanauskunft die Fu�note "Verst�rkerfahrt. Kann jederzeit ausfallen. Bus ist in der Regel als Linie 'V' beschildert."
714	Rail Replacement Bus Service (SEV)
715	Demand and Response Bus Service (anrufpflichtige Verkehre: ALT, Rufbus, Multibus, Netliner)

Rufnummern und Hinweise f�r Anruf-Verkehre:
===========================================
Bitte �bernehmen Sie die anrufpflichtigen Fahrten nur dann, wenn Sie sicherstellen k�nnen, dass auch die Rufnummern mit ausgeben werden k�nnen. Ansonsten entsteht hier keine f�r den Fahrgast wirklich nutzbare Information.
Nutzen Sie gegebenenfalls den ebenfalls verf�gbaren HAFAS-Datensatz.

Bei Multibus und Netliner handelt es sich um Verkehre, die ein gr��eres Gebiet ohne festen Fahrplan bedienen. Der Fahrplan ist hier nur eine modellhafte Darstellung und kann bei der Buchung deutlich abweichen.

2ALT, 6ALT, 12ALT, 15ALT, 17ALT, 26ALT, 27ALT, 30ALT, 37ALT, 46ALT, 48ALT, 55ALT, 57ALT, 74ALT, 77ALT, EW2ALT, EW4ALT, EW6ALT, W�1:
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
Anmeldung 30 Minuten vor Abfahrt Tel: 02 41/16 88 33 22 oder netliner.aseag.de. Die tats�chlichen Fahrzeiten erhalten Sie nach Buchung.

Herausgeber
===========
AACHENER VERKEHRSVERBUND GMBH
Neuk�llner Stra�e 1
52068 Aachen
AVV-Linien 23, 30 und 43
Haltestelle ASEAG
Internet: www.avv.de
eMail: info@avv.de
----------------------------------------------------
Aufsichtsratsvorsitzender: Wilhelm Paffen
Gesch�ftsf�hrer:
Hans-Peter Geulen
Dipl.-Ing. (FH) Heiko Sedlaczek
---------------------------------------------------
Registergericht Aachen, 
Handelsregister Abt. B Nr. 5952
USt-Id-Nr.: DE 169 963 856
Steuernummer: 201 59403252

Fragen
======
Bei Unklarheiten kann nur in ganz geringem Umfang und ohne Priorit�t ein Support geleistet werden. Wir bitten um Verst�ndnis.
