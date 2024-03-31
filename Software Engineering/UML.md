https://pdf.plantuml.net/PlantUML_Language_Reference_Guide_en.pdf

Class diagram

`+`  : public
`-`  : private
`#`  : protected
`_`  : static

| class name                             |
| -------------------------------------- |
| + variable_name: type                  |
| -------------------------------------- |
| + method_name(parameters): return_type |


Class relationship

1. Association
can call

A ---- B

both the class can call each other

it can be Unidirectional Association 
A ----> B 
A can call B, but B can not call A


Multiplecity


1. Aggregation
has an instance of

A aggregation B
B can exist without A


2. Composition
A composition B
B can not exist without A

![HI](https://plantuml.corp.amazon.com/plantuml/form/encoded.html#encoded=PL512eCm43mthzXpnGz84IdjpOFW2nOJIcXC9Db2I-dVcwBHZTrJTcROcTqqWT3JOpGYrc0m1EZGtxMzjOxWBGu5M1nL1Jtv20g8LO2ovD4EAbJGwa2dwz9tQ9Mfa-YfQHN4TqPA7IQ3hxD3Bokui6uHJ7EAVdBha6w3Ql59SJFlc7WZaYS7kHF7sUmPPbSubcNkyaScfpsHxRNZc6CyVQEi_Ft25m00)



```plantuml
@startuml



class ParkingLot {
	+ name: String
    + entrances: List<EntrancePanel>
    + exits: List<ExitPanel>
    + displayBoard: DisplayBoard
    + parkingSpots: List<ParkingSpot>
}

class EntrancePanel {
}

class ExitPanel {
}

class DisplayBoard {
}

class ParkingSpot {
}

ParkingLot *-- EntrancePanel
ParkingLot *-- ExitPanel
ParkingLot *-- DisplayBoard
ParkingLot *-- ParkingSpot


@enduml
```


---

```mermaid

classDiagram
	A <|-- B: A is a B (Inheritance)
	C <-- D: C has a D

```


```mermaid

classDiagram
	class B {
		<<interface>>
	}
	
	class A
	A ..|> B: A implements B
```

