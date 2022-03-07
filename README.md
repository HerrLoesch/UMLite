![](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)

# Aufbau
Im ersten Kapitel dieses Dokuments wird zunächst erläutert was sich hinter UMLite verbigt. Die wichtigsten Kapitel folgen darauf und sind [Wichtige Darstellungselemente](#wichtige-darstellungselemente), [Strukturdiagramme](#strukturdiagramme) und [Verhaltensdiagramme](#verhaltensdiagramme). Im letzten Kapitel wird das Ganze um Anmerkungen und Tipps erweitert, die beim Einsatz von UMLite helfen können. In jedem Kapitel werden zunächst zwingende Festlegungen beschrieben, bevor diese dann um optionale Dinge erweitert werden. Auf diese Weise sollte es möglich sein UMLite leichter in konkreten Situationen und mit unterschiedlichen Werkzeugen zu verwenden.

- [Aufbau](#aufbau)
- [Motivation](#motivation)
- [Wichtige Darstellungselemente](#wichtige-darstellungselemente)
  - [Bausteine](#bausteine)
  - [Beziehungen](#beziehungen)
  - [Kommentare](#kommentare)
- [Strukturdiagramme](#strukturdiagramme)
  - [Komponentendiagramm](#komponentendiagramm)
  - [Klassendiagramm](#klassendiagramm)
  - [Paketdiagramm](#paketdiagramm)
- [Verhaltensdiagramme](#verhaltensdiagramme)
  - [Aktivitätsdiagramm](#aktivitätsdiagramm)
  - [Sequenzdiagramm](#sequenzdiagramm)
- [Anmerkungen & Tipps](#anmerkungen--tipps)

# Motivation

Die [UML](https://de.wikipedia.org/wiki/Unified_Modeling_Language) (Unified Modeling Language) ist eine weit verbreitete grafische Modellieungssprache die von der [Object Management Group](https://www.omg.org/spec/UML/) entwickelt wurde. Sie wird von vielen Werkzeugen unterstützt und von Softwarearchitekten weltweit genutzt um Softwarestrukturen und deren interne Abläufe näher zu beschreiben. Der größte Vorteil der Sprache ist ihre Standartisierung, der größte Nachteil ihr Umfang. Man kann mit der UML Zusammenhänge sehr detailiert beschreiben, muss aber recht genau wissen wie man dabei vorgeht um nicht ggf. Verwirrung zu stiften. 

Dieser beschriebene Umfang und die Komplexität wird schon sichtbar, wenn man die verschiedenen Diagrammtypen der UML betrachtet (ursprüngliche Quelle: [Wikipedia]()):

![Diagrammarten](images/Diagrammarten.svg)


Das Ziel dieser Seite ist es, eine vereinfachte Form der UML zu beschreiben die folgende Anforderungen erfüllt:
- Sie sollte leicht verständlich und schnell zu lernen sein.
- Sie sollte ohne größeren Aufwand mit verschiedenen Zeichenwerkzeugen genutzt werden können.
- Sie sollte möglichst mit der UML kompatibel sein.

Außerdem wird darauf geachtet, dass alle Beschreibungen möglichst einfachen und damit leicht verständlich sind.

Um die Komplexität zu verringern, werden nachfolgend vorallem die Diagramme beschrieben, die am häufigsten in der Praxis anzutreffen sind oder als besonders nützlich gelten. Teilweise findet auch absichtlich eine Vermischung von Diagrammtypen der UML statt.

# Wichtige Darstellungselemente

## Bausteine
Mit UMLite wird dargestellt wie Software aufgebaut ist und wie ihre einzelnen Bausteine interagieren. Bausteine sind dabei alle Bestandteil die näher beschrieben werden sollen. Sie werden als *Rechtecke* dargestellt. Um sie näher zu beschreiben, können Anmerkungen über dem Namen der Bausteine eingetragen werden. Diese Anmerkungen sind von spitzen Doppelklammern umgeben um sie vom Namen abzuheben.

![Bestandteile](images/Bausteine.svg)

Im Beispiel haben wir es mit unterschiedlichen Arten von Bausteinen zu tun. Es gibt beispielsweise die Kaffeemaschine, die ein komplettes System sein kann und es gibt die Komponente Brüheinheit, die in der Kaffeemaschine das Aufbrühen des Kaffees übernimmt. Nähere Erläuterungen zu den Anmerkungen und den unterschiedlichen Arten von Bausteinen finden sich im Kapitel [Strukturdiagramme](#strukturdiagramme).

## Beziehungen
**Verpflichtend**

Bausteine allein machen noch keine Software, sie müssen auch miteinander interagieren. Durch diese Interaktionen ergeben sich Beziehungen zwischen den Bestandteilen. Diese Beziehungen können unterschiedlicher Art sein:

![Beziehungen](images/Beziehungen.svg)

1. Eine Bezieung die nicht näher beschrieben werden muss, nicht näher beschrieben werden kann oder bei der beide Bestandteile voneinander abhängen, wird als einfacher Strich dargestellt.
2. Ergibt sich aus der Beziehung eine direkte Abhängigkeit eines Bestandteils zu einem anderen, wird dies durch einen **Pfeil mit offener Spitze** dargestellt. Abhängigkeit bedeutet dabei, dass der Bestandteil von dem der Pfeil ausgeht den Bestandteil braucht auf den der Pfeil zeigt.
3. Die **geschlossene Spitze** ist ein Spezialfall der im Kapitel [Strukturdiagramme](#strukturdiagramme) näher erläutert wird. Er bedeutet, dass der Baustein von dem der Pfeil ausgeht spezialisierter ist, als der auf den der Pfeil zeigt. Umgekehrt ist der Baustein auf den der Pfeil zeigt damit allgemeiner formuliert als der von dem der Pfeil ausgeht.

**Funcfact**: Die vielen verschiedenen Arten von Pfeilen in der UML waren einer der Gründe warum UMLite formuliert wurde.

**Optional**

In fast jedem Zeichenprogramm können unterschiedliche Linientypen verwendet werden. UMLite schreibt nicht vor ob nun eine Linie durchgezogen, gestrichelt oder gepunktet ist. Je nach Auswahl können damit aber unterschiedliche Warnehmungen erreicht werden. So sieht man eine durchgezogene Linie viel deutlicher als eine gestrichelte, weshalb sie allgemein als wichtiger wahrgenommen wird.

![Linientypen](images/Linientypen.svg)

**Hinweis**: Die UMLite schreibt keine Linientyp vor.Trotzdem sollte doch darauf geachtet werden, dass beim Zeichnen immer auch ein gleiches Vorgehen genutzt wird. Daher sollte man sich bewusst entscheiden ob man nun bevorzugt gestrichelte, gepunktete oder durchgezogene Linien verwendet. Im besten Fall nutzt man einfach die Standardeinstellung des verwendeten Zeichenprogramms.

## Kommentare
**Verpflichtend**

Kommentare sind keine konkreten Bausteine, sondern erweiterte Beschreibungen. Sie sind in aller Regel gelb eingefärbt und verfügen rechts oben über eine eingeknickte Ecke. Weiterhin werden sie durch eine gerade und gestrichelte Linien mit dem Bestandteil verbunden, den sie näher beschreiben.

![Kommentare](images/Kommentare.svg)

**Alternativ**

Nicht jedes Zeichenprogramm bietet die Möglichkeit ein Rechteck mit eigeknickter Ecke zu verwenden. Aus diesem Grund kann man auf andere Darstellungsformen ausweichen. Es bietet sich aber an, diese dann immer gelb einzufärben. Sollte man Rechtecke als Kommentare verwenden sollte die Anmerkung *Kommentar* verwenden um Missverständnisse zu vermeiden.

![Alternative Kommentare](images/Alternativekommentare.svg)

# Strukturdiagramme

## Komponentendiagramm

## Klassendiagramm

## Paketdiagramm

# Verhaltensdiagramme

## Aktivitätsdiagramm

## Sequenzdiagramm

# Anmerkungen & Tipps

