## NETITS_Grundlagen LEK / IHK PRÜFUNG

---


### Inhaltsverzeichniss




[02 Topologien](#g2)

[03 (Referenzmodelle)](#g3)

[04 (Ethernet, RJ45, LWL, strukturierte)](#g4)

[05 (Wifi)](#g5)

[08 (OSI2, SPT, MAC)](#g8)

[10 (IP, Subnetting)](#g10)

[11 (IP Headeranalyse, Wireshark)](#g11)

[12 (IPv6)](#g12)

[15 (Routing RIP)](#g15)

[16 (Routing OSPF)](#g16)

[18 (DNS)](#g18)

[19 (DHCP)](#g19)

[21 (VLAN)](#g21)

[22 (Netztools)](#g22)

[23 (Firewalls)](#g23)

---












<a name="g2"></a>

# 02 (Topologien)

    Token Ring ("vielleicht , guckts euch mal an")

<a name="g3"></a>

# 03 (Referenzmodelle)

> JÖRG sagt :
>
>
> "OSI ganz wichtig"
> -> AUFBAU OSI Referenzmodell ("Das Modell an dem wir kommunikation definieren")
>("ES KÖNNTEN fragen kommen wie was macht die Sicherungsschicht")
>

> Schicht 1 bis 2 = Pysische Schichten
>
> Schicht 3 - 7 = Logische Schichten

<ul>

__1. BITÜBERTRAGUNSSCHICHT__

    Beschreibt den Zugriff auf das Netzwerk-Medium

    Beschreibt die physischen Anschlüsse und die Umsetzung der Daten in Signale

    Ausserdem Definition der Datenübertragungsrate und ob es eine unidirektionale oder bidirektionale Kommunikation ist




__2. SICHERUNGSSCHICHT__

    soll für eine Fehlererkennung sorgen
    
    Pakete der Vermittlungsschicht in Rahmen der Sicherungsschicht verpackt und übertragen

    Definiert Mac adressen
    sorgt für Datenübertragung auf physischer ebene
    
    Für die Zustellung beim Empfänger sind physische Adressen erforderlich
    MAC-Adressen
    Befinden sich auf der Sicherungsschicht


> JÖRG sagt :
>
>"wie geht die sicherungsschicht mit Fehlerhaften rahmen um" - eine meiner lieblingsfragen"
>
> --> Reparieren oder Verwerfen .. Antwort = Verweren ;) 

__4.VERMITTLUNGSSCHICHT__
    
    Das ist die erste logische Netzwerkschicht

    Auf dieser Schicht werden logische Adressen definiert
    = IP-Adressen

    Auf dieser Schicht werden Segmente der Transportschicht in Pakete verpackt




__4. TRANSPORTSCHICHT__

> JÖRG sagt :
>
> Ein Segment kann aus mehreren Paketen bestehen ,ein Paket kann aus mehreren Rahmen bestehen

    Hier werden Segmente transportiert

    Tatsache: Ende-2-Ende-Verbindung

    Zuordnung der Kommunikation zu den laufenden Prozessen
    > Ports werden durch Portnummern adressiert
    Sorgt für die korrekte Auslieferung an die richtigen Anwendungen




    
__5. SITZUNGSSCHICHT__

    Soll eigentlich dazu dienen:
    > Aufbau
    > Überwachung
    > Beendigung einer Sitzung


__6. DARSTELLUNGSSCHICHT__
    
    In dieser Schicht sind Regeln zur Formatierung (Präsentation) von Nachrichten enthalten

    Erweiterung von Datensätzen mit Feldern wie Name, Artikelnummer,…

    Kompression und/oder Verschlüsselung der Daten werden der Darstellungsschicht zugedacht

    In der Praxis aber kaum genutzt da dieses direkt von den Anwendungen gemacht wird



__7. ANWENDUNGSSCHICHT__

    Hier entstehen und werden empfangen die eigentlichen Nachrichten

    Also hier sind die echten Anwendungen zu Hause
    Webserver
    Mailprogramm

    In Nerdsprache: HTTP, FTP, SMTP, POP3, IMAP, DNS, SSH, Telnet, ….


---

!['Test'](https://i.imgur.com/TcmlgVL.png)




</ul>

<a name="g4"></a>

# 04 (Ethernet, RJ45, LWL, strukturierte)

__Primärverkabelung__

Gebäudeübergreifende Verkabelung
Auch Campusverkabelung oder Geländeverkabelung genannt
Besteht i.d.R. aus redundanten Kabeltrassen mit LWL-Leitungen
Relativ große Entfernungen sind dadurch überbrückbar

__Sekundärverkabelung__

Bildet das gebäudeinterne Backbone Netzwerk und verbindet den Gebäudeverteiler mit dem Etagenverteiler
Hier kommen Kupfer- und/oder Lichtwellenleiter zum Einsatz

__Tertiärverkabelung__

Sternförmige Verkabelung auf Etagenebene
Verbindung von Anschlußdosen mit den Etagenverteilern
Typischerweise Kupferkabel (Twisted-Pair)

<a name="g5"></a>

# 05 (Wifi)

> __JÖRG sagt__  :
> 
> Wifi ist ein interrsantes Thema
könnte jeden von uns interessieren :D.
>
> Es könnte eine Frage kommen wie :
> Ihr habt folgendes Bürogebäude...
> Was würdet ihr machen um ausleuchtung zu
> verbessen ;) , Welche Einstellmöglichkeiten habt ihr ?
>
> Zuviele WLANS in der Umgebung , was könnt
> ihr tun um Signal zu verbessern ;) ?

&nbsp;
&nbsp;
&nbsp;

    Heatmap erstellen und überprüfen ob der Access Point optimal positioniert ist

    Wifi-Kanal-Analyse um zu sehen, wer funkt noch alles auf diesem Kanal
    Im Zweifel Kanäle durchprobieren
    Eventuell von 2,4 GHz auf 5 GHz wechseln und geringere Ausbreitung in Kauf nehmen

    Überprüfen ob alle Empfänger in Reichweite des Wifi sich befinden
    Software-Updates der Wifi-Geräte 

    Problem: DHCP
    Sind mehrere DHCP-Server vorhanden kann es zu Problemen kommen







<a name="g8"></a>

# 08 (OSI2, SPT, MAC)

> JÖRG sagt :
> 
> Sicherungschicht .. da könnten 
so fragen kommmen wie "Was macht das 
Ding " ;) ?
>
>  Spanning tree wozu was macht er
>  wie arbeitet er
>
> In der Ihk Prüfung könnte sowas kommen
> wie "welche Verbindung wird durch 
> spanning Tree abgeschlatet ?
> Immer die langsamste ;).
>
> Was ist eine MAC Adresse ? Aufbau usw
> Broadcast , Broadcast Domäne , Was ist das ;).

    __Zur Verhinderung der Kreise(infinite loop)__
    Es wird ein Spannbaum kreiert (Spanning Tree)
    Diesen erstellen die Bridges selbst mittels Spanning Tree Algorithmus
    Ziel ist es einen Kreis zu verhindern
    Dazu werden einige Ports der Bridge logisch entfernt
    So dass kein Kreis entsteht

    Damit der Spanning Tree Algorithmus funktioniert muß jede Bridge eine eindeutige ID besitzen

    __Bridge Protocol Data Unit (BPDU)__
    Dieses tauschen die Bridges als Broadcast allen anderen Bridges mit
    Wieso Broadcast?
    Weil die Bridges sich erst einmal untereinander nicht kennen

    Ein Broadcast ist ein Senden an ALLE Stationen
    Alle Stationen reagieren auf diesen Broadcast und verarbeiten diese Rahmen
    Eine Broadcast-Adresse auf OSI-Schicht 2 sieht wie folgt aus:
    FF – FF – FF – FF – FF – FF – FF

    MAC adresse ist 48 Bit lang  






<a name="g10"></a>

# 10 (IP, Subnetting)

> JÖRG sagt :
> ich geb euch ne Adresse und ihr müsst
schauen ob das funktionier (subnetting ausrechnen)

<a name="g11"></a>

# 11 (IP Headeranalyse, Wireshark)

> JÖRG sagt :
> Ich glaub der Felix ist falsch verkabelt . Macht mal ne Header Analyse um den
Jungen zu helfen.

    RECHNUNG
    Ihr habt den folgenden Netzwerk-Mitschnitt erhalten (Wireshark):

    45 00 05 ac 11 9c 40 00 	3b 06 7f 37 c3 0a 24 bc 
    c0 a8 01 0a 00 50 cc 9b 	4c 8e 3b 94 3c df c2 2b
    80 18 01 e6 a5 11 00 00 	01 01 08 0a 1d 14 bf a4
    00 35 …

    Um was für ein IP-Paket handelt es sich hier (IPv4 oder IPv6)?
    Ermittelt die Quell- und Ziel-IP-Adresse!
    Wie lang ist das komplette Datenpaket?



<a name="g12"></a>

# 12 (IPv6)
> JÖRG sagt :
> 
> Was ist Slaac ?
> WAS AUTOCONFIGURATION ?

    IPv4 – 32 Bits = 4 Bytes = 4.294.967.296 Adressen = ca. 4,3 Milliarden Adressen

    IPv6 = 128 Bits = 16 Bytes = 3,4*1038 = ca. 340 Sextimillionen Adressen

    Im IPv6 kann jeder Host sich selbst konfigurieren
    Dazu braucht er eine MAC-Adresse und muß seinen zuständigen Netzwerkrouter finden können
    Zunächst einmal bekommt der Host eine link-local-Adresse
    Es ist erst einmal bei IPv6 kein DHCP zur Autokonfig notwendig

    Man nennt das SLAAC (Stateless Address Auto Configuration)
    Hier werden link-locale-Adressen produziert



<a name="g15"></a>

# 15 (Routing RIP)
> JÖRG sagt :
> 
> solltet ihr wissen

    Routing beschreibt die Weiterleitung von IP-Paketen
    Dazu notwendig ist eine Wegebestimmung 

    Nur so weiß der Router auf welchem Port welche Pakete weitergeleitet werden sollen

    OSI-3 ist die Schicht auf dem Router arbeiten
    Denn zum Routen werden die IP-Adressen benötigt
    Und eine Tabelle, aus der hervorgeht auf welchem Port welche Netzwerke zu finden sind
    Die sogenannte lokale Routingtabelle
>    

    Beim Starten eines Routers kennt dieser nur seine direkt angeschlossenen Netzwerke. Ein neuer Router sendet daher auf jedem RIP-konfigurierten Interface eine Aufforderung an alle seine Nachbarn mit der Bitte um Zusendung ihrer vollständigen Routingtabelle. Aus den erhaltenen Antworten errechnet der fragende Router die ersten Einträge seiner noch ungefüllten Routingtabelle. Im Anschluss daran schickt er ein triggered Update mit seiner neu erstellten Routingtabelle an alle RIP-Nachbarn, so dass diese ihrerseits über eventuelle neue Wege informiert werden.

    NUR DIREKTE BEKANNSTSCHAFT :
    Netz 1 – Router A ------- Router B ------- Router C

    Das Netz 1 wird somit erreicht von:

    Router A mit dem Hop 0
    Router B mit Hop 1 über Router A
    Router C mit Hop 2 über Router B und Router A.


<a name="g16"></a>

# 16 (Routing OSPF)
> JÖRG sagt :
> 
> solltet ihr wissen und statisches routing auch für  IHK prüfung
>
> ihk Was unterschied rip und ospf ?

    Im Gegensatz zu OSPF und  kennt ein RIP-Router immer nur seine direkten Nachbarn

    Die nur direkte Bekanntschaft seiner Nachbarn ist auch das größte Problem von RIP. Zum einen ergeben sich hohe Konvergenzzeiten und das Count-to-Infinity-Problem. Infinität bezeichnet die Unerreichbarkeit eines Ziels und wird bei RIP mit dem Hop-Count 16 angegeben.

    OSPF ist ein moderneres Routingprotokoll

    OSPF nutzt Kosten als Metriken anstelle von Hops
    Kosten orientieren sich an der Bandbreite

    OSPF erreicht schnell den Zustand der Konvergenz

    OSPF baut im Gegensatz zu Rip eine Topologie-Datenbank auf

    OSPF erkennt schneller den „Tot“ einer Route


<a name="g17"></a>

# 17 (TCP)
> JÖRG sagt :
> 
> Was ist ein well known Port
> Was ist port 22 .. xyz standart ports ...
> Unterschied tcp udp
> 3 Wege Handshake solltet ihr kennen !
> Viele IPV4 Fragen in der Ihk !

    Aufgabe der Transportschicht :

    Bereitstellung einer Ende-zu-Ende-Verbindung

    Dienst zur Intreprozesskommunikation

    Herausforderungen der Transportschicht :

    Es ist nicht sichergestellt, dass alle IP-Pakete in der richtigen Reihenfolge ankommen

    Es ist nicht sichergestellt, dass alle IP-Pakete überhaupt ankommen

    Man unterscheidet:
    Well known Ports: 0 – 1023
    Registered Ports: 1024 – 49151
    Private Ports: 49152 – 65535

    __UDP__
    Verbindungsloses Protokoll
    Bedeutet: die Daten werden ohne den Aufbau einer Verbindung versendet
    Es findet keine Sicherung der Datenübertragung statt
    Übertragungen werden also nicht vom Empfänger beim Sender bestätigt



[![Well known Ports](https://i.imgur.com/H3Cnxqs.png)](https://i.imgur.com/H3Cnxqs.png)

[![TCP 3 wege handshake](https://i.imgur.com/SI9Vaht.png)](https://i.imgur.com/SI9Vaht.png)







<a name="g18"></a>

# 18 (DNS)
> JÖRG sagt :
> 
> Was ist DNS , Wie funktionierts ?
> Vielleicht wie ist es aufgebaut ?
> Wichtig ;)

    DNS ist eine Namensauflösung von Domainnamen zu IP-Adressen

    Domain-Name Beispiel: www.keine-schleichwerbung.eu 

    Mittels DNS-Anfrage wird die richtige IP-Adresse zum Domainnamen herausgesucht
    Die Verbindung findet auf IP-Ebene statt

    __AUFBAU__
    DNS ist hierarchisch in einer Baumstruktur organisiert
    Die Informationen und Zuordnungen sind in separate Teile organisiert und im gesamten Internet auf Nameservern verteilt
    Angefangen von der Wurzel werden die Top-Level-Domains (TLD) andressiert
    Danach schließen sich die individuellen Domainnamen an
    Vollständige Domainnamen werden als Full Qualified Domain Name (FQDN) bezeichnet
    Ein FQDN kann sein: hostname.domainname.tld.
    Beispiel: ESMAD005.schleichwerbung-consulting.eu.

[![Strunktur DNS](https://i.imgur.com/glKlcjR.png)](https://i.imgur.com/glKlcjR.png)

    DNS-Anfragen werden via UDP auf Port 53 gestellt
    Die Antworten werden per UDP oder TCP an die Clients versandt (max. 512 Bytes)

    Alternative zum DNS
    Die Datei /etc/hosts unter Linux beispielsweise
    Enthält ebenfalls Domain Namen zu IP Adressen



<a name="g19"></a>

# 19 (DHCP)
> JÖRG sagt :
> 
> Wie funktioniert DHCP ?
> Harmlos ;).

    DHCP ermöglicht die Zuweisung von
    IP-Adresse
    Subnetzmask
    Default-Gateway
    Nameserver
    DHCP verwendet UDP auf Port 67 (Server) bzw. 68 (Client)
    Sinnvoll insbesondere bei mobilen Endgeräten

    __ARBEITSWEISE DHCP__
    1

    Wenn wir Client 1 einschalten sendet dieser einen DHCP-Discover als BC ins Netz

    IP-Adresse Sender: 0.0.0.0
    IP-Adresse Empfänger: 255.255.255.255

    2
    Jeder erreichbare DHCP-Server sendet darauf hin ein Adressangebot (DHCP-Offer) -> als BC

    3
    Der Client nimmt ein Adressangebot an, in dem er die Anfrage mittels einem DHCP-Request beantwortet

    Das wird ebenfalls als BC versandt; die Nachricht enthält die gewünschte DHCP-Server-ID

    4
    Der DHCP-Server bestätigt die Annahme mittels DHCP-Ack und trägt die IP als „verliehen“ (Lease) in seine DB ein

    5
    Bevor der Client nun die IP verwendet prüft er erst einmal ob die IP nicht schon vergeben ist

    Mittels ARP – falls schon vergeben lehnt der Client den Request ab.

    Aktive Clients verlängern die Lease in dem Sie nach der Hälfte des Verfallsdatums einen erneuten DHCP-Request schicken

![BILD](https://i.imgur.com/XiKtMkU.png)


<a name="g21"></a>

# 21 (VLAN)
> JÖRG sagt :
> 
> Wofür , was machen , funktion ?
> Wichtiges Thema !

    Ein Virtual Local Area Network (VLAN) ist ein logisches Teilnetz innerhalb eines Switches bzw. eines gesamten physischen Netzwerks.

    Jedes VLAN bildet wie ein normales (physisches) LAN auch eine eigene Broadcast-Domäne. Der Verkehr zwischen VLANs wird wie bei physischen LANs auch über Router oder Switches vermittelt. 

    Moderne Switches stellen diese Funktion intern zur Verfügung – man spricht dann von sogenannten Layer-3-Switches.

    __WIKIPEDIA__
    Ein Virtual Local Area Network (VLAN) ist ein logisches Teilnetz (Segment (Netzwerk)) innerhalb eines Switches bzw. eines gesamten physischen Netzwerks. Es kann sich über mehrere Switches hinweg ausdehnen. Ein VLAN trennt physische Netze in Teilnetze auf, indem es dafür sorgt, dass VLAN-fähige Switches Frames (Datenpakete) nicht in ein anderes VLAN weiterleiten (obwohl die Teilnetze an gemeinsamen Switches angeschlossen sein können).

    ++ VORTEILE ++
    Flexibilität
    bei der Zuordnung von Endgeräten zu Netzwerksegmenten, unabhängig vom Standort der Basisstation.

    Performance-Aspekte
    So kann zum Beispiel ein bestimmter Datenverkehr wie VoIP in einem VLAN erfolgen, das bei der Übertragung priorisiert wird. 

    Sicherheitsaspekte
    VLANs können Netze gegen Ausspionieren und Abhören besser absichern als geswitchte Netze.


<a name="g22"></a>

# 22 (Netztools)
> JÖRG sagt :
> 
> Ping und Tracert kennen wir !

    Ping ist ein Diagnose-Werkzeug, mit dem überprüft werden kann, ob ein bestimmter Host in einem IP-Netzwerk erreichbar ist.

    Ping sendet ein ICMP(v6)-„Echo-Request“-Paket (ping, ICMP-Pakettyp 8 (0x08)) an die Zieladresse des zu überprüfenden Hosts. Der Empfänger muss, sofern er das Protokoll unterstützt, laut Protokollspezifikation eine Antwort zurücksenden:

    Traceroute ist ein Computerprogramm, das ermittelt, über welche Router und Internet-Knoten IP-Datenpakete bis zum abgefragten Rechner gelangen.

    Traceroute sendet mehrfach IP-Datenpakete vom Typ ICMP Echo Request an den Ziel-Host, beginnend mit einer Time to Live (TTL) von 1. Der erste Router, der das Datenpaket weiterleiten soll, zählt den Wert der TTL um eins herunter auf 0, woraufhin er es nicht weiterleitet, sondern verwirft.

<a name="g23"></a>

# 23 (Firewalls)

> JÖRG sagt :
> 
> Was ist eine Firwall , Was macht eine Firewall nicht
> Wie funktioniert das abarbeiten des Regelwerks ?

    Firewalls werden dazu genutzt
    Den Traffic in Netzwerken zu filtern

    Nicht um Netzwerke zu segmentieren!!

    Anhand von definierten Entscheidungsmodellen wird entschieden
    Ob Datenpakete in das Netzwerksegment (oder innerhalb der Maschine) weitergeleitet werden oder nicht

    Es gibt statische und dynamische Firewalls
    Firewalls arbeiten nach definierten Regeln
    Zeilenweise Abarbeitung!!

    Paketfilterung
    Es werden Datenpaket auf OSI 3 und OSI 4 analysiert
    Filterung kann erfolgen nach
    Protokolltypen (UDP/TCP)
    Nach Ports/Sockets
    Unidirektional/bidirektional
    Sind zumeist statische Regeln, die der Admin eintragen muß

    Beispiel-Regelwerk:
    Aus dem Internet sind zum Mailserver in der DMZ Mail-Dienste (SMTP – TCP-Port 25, POP3 – TCP-Port 110 und IMAP – TCP-Port 143) erlaubt.
    Der Mailserver darf aus der DMZ in das Internet Mails per SMTP verschicken und DNS-Anfragen stellen.
    Aus dem lokalen Netz sind Administrationsdienste (SSH, Remote Desktop, Backup – TCP-Port 22) zum Mailserver erlaubt.
    Alle anderen Pakete in oder aus der DMZ werden in eine Logdatei geschrieben und danach verworfen












# NEBENBEI ERWÄHNT

RIP = ROUTING INFORMATION PROTOCOL , ( über UDP)
RUDIMENTÄT Wissen was ist UDP , TCP , IPV4 , IPV6


---
*Exclusiv für den Cool Kids Club*
