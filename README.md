![](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)

![](images/logo.png)

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

Die [UML](https://de.wikipedia.org/wiki/Unified_Modeling_Language) (Unified Modeling Language) ist eine weit verbreitete grafische Modellierungssprache die von der [Object Management Group](https://www.omg.org/spec/UML/) entwickelt wurde. Sie wird von vielen Werkzeugen unterstützt und von Softwarearchitekten weltweit genutzt um Softwarestrukturen und deren interne Abläufe näher zu beschreiben. Der größte Vorteil der Sprache ist ihre Standardisierung, der größte Nachteil ihr Umfang. Man kann mit der UML Zusammenhänge sehr detailliert beschreiben, muss aber recht genau wissen wie man dabei vorgeht um nicht ggf. Verwirrung zu stiften. 

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

1. Eine Beziehung die nicht näher beschrieben werden muss, nicht näher beschrieben werden kann oder bei der beide Bestandteile voneinander abhängen, wird als einfacher Strich dargestellt.
2. Ergibt sich aus der Beziehung eine direkte Abhängigkeit eines Bestandteils zu einem anderen, wird dies durch einen **Pfeil mit offener Spitze** dargestellt. Abhängigkeit bedeutet dabei, dass der Bestandteil von dem der Pfeil ausgeht den Bestandteil braucht auf den der Pfeil zeigt.
3. Die **geschlossene Spitze** ist ein Spezialfall der im Kapitel [Strukturdiagramme](#strukturdiagramme) näher erläutert wird. Er bedeutet, dass der Baustein von dem der Pfeil ausgeht spezialisierter ist, als der auf den der Pfeil zeigt. Umgekehrt ist der Baustein auf den der Pfeil zeigt damit allgemeiner formuliert als der von dem der Pfeil ausgeht.

**Funcfact**: Die vielen verschiedenen Arten von Pfeilen in der UML waren einer der Gründe warum UMLite formuliert wurde.

**Optional**

In fast jedem Zeichenprogramm können unterschiedliche Linientypen verwendet werden. UMLite schreibt nicht vor ob nun eine Linie durchgezogen, gestrichelt oder gepunktet ist. Je nach Auswahl können damit aber unterschiedliche Wahrnehmungen erreicht werden. So sieht man eine durchgezogene Linie viel deutlicher als eine gestrichelte, weshalb sie allgemein als wichtiger wahrgenommen wird.

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
Strukturdiagramme zeigen wie etwas aufgebaut ist. Sie stellen also dar welche Bausteine es gibt, welche Eigenschaften diese haben und welche Beziehungen zwischen ihnen bestehen.
## Komponentendiagramm

**Grundsätzlicher Aufbau**

Komponentendiagramme werden immer dann genutzt wenn eine Struktur ohne größere Details dargestellt werden soll. Es geht bei diesen Diagrammen mehr darum die wichtigsten Bestandteile und deren Abhängigkeiten zu erklären, als ihren detailierten Aufbau. In dem Bausteine in einem Komponentendiagramm als *Komponenten*, *Systeme*, *Subsysteme* oder ähnliches bezeichnet werden, wird nur der Hinweis darauf gegeben, dass sie noch feinere Strukturen besitzen, die für die aktuelle Darstellung aber nicht von Bedeutung sind.

![Darstellungselemente eines Komponentendiagramms](images/Komponentendiagramm-Darstellungselemente.svg)

Insofern es möglich ist, kann auf die Anmerkung aber auch verzichtet werden. In diesem Fall sollte das Rechteck aber ein Symbol enthalten, die es als Komponentendarstellung kennzeichnet. Dieses Symbol besteht aus drei übereinander gelegten Rechtecken. Zusätzlich können auch die Abhängigkeiten weiter verfeinert werden, indem die Schnittstellen in *angeboten* und *benötigt* unterschieden werden. Angebotene Schnittstellen werden von einer Komponente zur Verfügung gestellt und können damit von anderen Komponenten genutzt werden. Benötigte Schnittstellen werden wiederum von einer Komponente gebraucht, damit diese ihre eigentliche Aufgabe erfüllen kann. Damit Schnittstellen besser wahrgenommen werden können, sollten diese außerdem über ein Quadrat, den sogenannten *Port*, auf der Seite der Komponente verfügen. Damit können sie besser von anderen Arten von Abhängigkeiten unterschieden werden.



**Beispiel mit verpflichtenden Inhalten**

Um es noch einmal zu verdeutlichen: Komponenten sind Bestandteile deren interner Aufbau nicht eindeutig definiert ist. In aller Regel handelt es sich um Bestandteile die intern in weitere Bestandteile zerlegt sein können, nach Außen aber als ein einzelner Bestandteil auftreten. 

Das klingt möglicherweise etwas verwirrend und deshalb soll es am Beispiel eines Kaffeevollautomaten erklärt werden. Dieser mahlt seine Bohnen selbst, verfügt über einen Wassertank, eine Brühgruppe und eine Auffangschale für die gemahlenen Kaffeebohnen. In einem Komponentendiagramm können all diese Bestandteile als Teil des Systems "Kaffeevollautmat" dargestellt werden. Zusätzlich werden ihre Interaktionspunkte und Schnittstellen eingezeichnet. Wichtig ist hierbei, dass die Darstellung nicht zu detailliert sein sollte, weil sie sonst unübersichtlich wird und schnell altert. Daher reicht es oft schon die Rechtecke mit entsprechenden Anmerkungen wie *Component* oder *System* zu versehen und deren Ports über duchgezogene Linien miteinander zu verbinden.

![Beispiel eines Komponentendiagramms](images/Komponentendiagramm-Beispiel.svg)

**Beispiel mit optionalen Inhalten**

Die einfache Darstellung lässt sich zwar in jedem Zeichenprogramm darstellen, ist aber ggf. nicht eindeutig genug. Je nach verfügbarer Symbolbibliothek macht es daher Sinn, auch die Schnittstellen und deren Charakter (angeboten oder benötigt) entsprechend darzustellen. Zusätzlich sollten das Komponentensymbol verwendet werden, damit sofort ersichtlich wird, dass in diesem Diagramm bewusst Details ausgespart wurden. Möchte man dann noch darstellt, dass die Komponenten durchaus eine unterschiedliche Komplexität haben, kann diese durch entsprechende Anmerkungen dargestellt werden. Hierbei werden oft folgende Begriffe verwendet:

- *System* - Eine sehr umfangreiche und komplexe Anordnung die alle weiteren Bestandteile enthält.
- *Subsystem* - Ebenfalls ein recht umfangreiches Gebilde, dass aber Teil eines umfassenden Systems ist.
- *Component* - Eine Komponente die in weitere feine Strukturen zerlegt werden kann, dabei aber nicht so komplex wie ein Subsystem oder System ist.

Es können auch weitere Begriffe genutzt werden, die aber sehr stark von den jeweiligen fachlichen und technischen Zusammenhängen bestimmt werden. Dazu zählen beispiwelsweise *Package*, *Module* oder *Assembly*

![Komplexbeispiel eines Komponentendiagramms](images/Komponentendiagramm-Komplexbeispiel.svg)

Je nach darzustellenden Zusammenhängen kann es bei einem Komponentendiagramm auch Sinn ergeben, entsprechende Nutzer und Nutzergruppen einzuzeichnen um darzustellen mit welchen Bestandteilen die *Akteure* direkt interagieren. In diesem Fall wird ein Strichmännchen verwendet.
## Klassendiagramm

## Paketdiagramm

# Verhaltensdiagramme

## Aktivitätsdiagramm

## Sequenzdiagramm

# Anmerkungen & Tipps

