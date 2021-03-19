## NETITS_Grundlagen LEK / IHK PRÜFUNG

---


### Inhaltsverzeichniss




[02_Topologien](#g2)

[03 (Referenzmodelle)](#g3)

[04 ((Ethernet, RJ45, LWL, strukturierte))](#g4)

[05 (Wifi)](#g5)

[08 (OSI2, SPT, MAC)](#g8)

[10 (IP, Subnetting)](#g10)

[11 (IP Headeranalyse, Wireshark)](#g11)

[12 (IPv6)](#g12)

[15 (Routing RIP))](#g15)

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



__6. ANWENDUNGSSCHICHT__

    Hier entstehen und werden empfangen die eigentlichen Nachrichten

    Also hier sind die echten Anwendungen zu Hause
    Webserver
    Mailprogramm

    In Nerdsprache: HTTP, FTP, SMTP, POP3, IMAP, DNS, SSH, Telnet, ….


---




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


<a name="g15"></a>

# 15 (Rouitng RIP)
> JÖRG sagt :
> 
> solltet ihr wissen

<a name="g16"></a>

# 16 (Routing OSPF)
> JÖRG sagt :
> 
> solltet ihr wissen und statisches routing auch für  IHK prüfung
>
> ihk Was unterschied rip und ospf ?

<a name="g17"></a>

# 17 (TCP)
> JÖRG sagt :
> 
> Was ist ein well known Port
> Was ist port 22 .. xyz standart ports ...
> Unterschied tcp udp
> 3 Wege Handshake solltet ihr kennen !
> Viele IPV4 Fragen in der Ihk !

<a name="g18"></a>

# 18 (DNS)
> JÖRG sagt :
> 
> Was ist DNS , Wie funktionierts ?
> Vielleicht wie ist es aufgebaut ?
> Wichtig ;)


<a name="g19"></a>

# 19 (DHCP)
> JÖRG sagt :
> 
> Wie funktioniert DHCP ?
> Harmlos ;).

<a name="g21"></a>

# 21 (VLAN)
> JÖRG sagt :
> 
> Wofür , was machen , funktion ?
> Wichtiges Thema !


<a name="g22"></a>

# 22 (Netztools)
> JÖRG sagt :
> 
> Ping und Tracert kennen wir !

<a name="g23"></a>

# 23 (Firewalls)

> JÖRG sagt :
> 
> Was ist eine Firwall , Was macht eine Firewall nicht
> Wie funktioniert das abarbeiten des Regelwerks ?

    pin udn traceoute








# NEBENBEI ERWÄHNT

RIP = ROUTING INFORMATION PROTOCOL , ( über UDP)
RUDIMENTÄT Wissen was ist UDP , TCP , IPV4 , IPV6


---
*Exclusiv für den Cool Kids Club*
