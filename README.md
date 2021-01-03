# Headline 1
## Headline 2
### Headline 3
#### Headline 4

This is a *bold* text. This is _emphasized_. [Linktext!](http://google.com)

Hallo Peter

* Sensordaten zur Steuerung von Raketen (SpaceX) 
* Incident Monitoring im eCommerce
* Analyse von Bilddaten 

# Notizen
## Layer und übliche Technologien
### Data Ingestion Layer
Technologien: Kafka  
Komponenten/Aufgaben: Sammelt erstmal Daten

### Speed Layer
Technologien: Spark, Flink  
Komponenten/Aufgaben: Verarbeitet Daten möglichst in Echtzeit, hält die Daten im RAM vor. 

### Batch Layer
Technologien: Hadoop  
Komponenten/Aufgaben: Master Dataset, Data Processing, Fehlerbehebung des Speedlayers

### Serving Layer
Technologien: Cassandra, HBase  
Komponenten/Aufgaben: Bereitstellung der aufbereiteten Daten

### Allgemein 
Zunächst erklären, was das ist, was das kann usw. ---> https://www.datenbanken-verstehen.de/lexikon/lambda-architektur/ Gut für Info Einleitung
Beispiel, warum für große Datenmengen diese Technologie von Vorteil ist. Warum würde z.B. keine relationale Datenbank reichen?

Ein wichtiges Anwendungsgebiet für die Lambda Architektur ist Big Data. Häufig stoßen relationale Datenbanken –oder auch allgemeiner ausgedrückt – herkömmliche Datenbanktechnologien bei sehr großen Datenmengen an ihre Grenzen. Probleme ergeben sich dabei aufgrund der Skalierbarkeit, aber auch aufgrund der Komplexität. 
Wird beispielsweise eine relationale Datenbank plötzlich um ein Vielfaches stärker genutzt als üblicherweise, kann sie möglicherweise nicht mehr so viele Anfragen (Requests) bearbeiten und gibt Zeitüberschreitungsfehler aus. Ein Workaround wäre hier, für die Anfragen eine Warteschlange zu eröffnen und diese dann mithilfe eines Worker-Prozesses gebündelt bearbeiten zu lassen. Dieser nimmt beispielweise 100 Ereignisse aus der Warteschlange heraus und fasst diese zu einer einzigen Datenbankaktualisierung zusammen. Wird die Datenbank nun noch stärker genutzt, kann der Worker nicht so schnell arbeiten wie die Schreibvorgänge stattfinden, mehrere Worker zusammen lösen das Problem nur kurzfristig. Eine weitere Möglichkeit, die relationale Datenbank an die veränderte Anzahl der Anfragen anzupassen, wäre das Sharding. Dies ist eine sogenannte horizontale Partitionierung. Datensätze, in denen die Werte innerhalb einer Tabellenspalte gleich sind, werden gemeinsam abgespeichert. Die Arbeitslast beim Schreiben wird durch dieses Verfahren auf mehrere Maschinen verteilt. Hierzu ist ein Script erforderlich, das die Datensätze auf mehrere Datenbanken verteilt. 
Wegen der Skripte und der unterschiedlichen Datenbanken, von denen möglicherweise immer mehr benötigt werden, steigt die Komplexität. Im Falle eines Hardwareausfalls oder einer nötigen Anpassung der Skripte, können Folgefehler entstehen oder es kann sogar zu Datenverlust kommen. Ein Beispiel wäre der Ausfall einer Festplatte: Auch wenn es ein Backup gibt, können Anfragen bis zur Behebung des Ausfalls verloren gehen.  NoSQL  wäre auch keine Patentlösung, weil wegen der begrenzten Datenmodelle sehr viele eigene Modifikationen notwendig werden können, wodurch die Datenbanken wiederum fehleranfällig werden können. 

