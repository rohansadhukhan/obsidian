#DesignPattern #Behavioral

**State** is a behavioral design pattern that lets an object alter its behavior when its internal state changes.


## Use Case Diagram

```uml
@startuml

(Idle State) as Idle

(Money State) as Money

(Product Selection State) as Selection

(Product Dispance State) as Dispance

Idle --> Money: Press insert money
Money --> Money: Inserting money
Money --> Idle: Cancel
Money --> Selection: Press select product
Selection --> Selection: Selecting product
Selection --> Idle: Cancel / Insufficient money
Selection --> Dispance
Dispance --> Idle: Dispence product

@enduml
```


| State             | Operation                 |
| ----------------- | ------------------------- |
| Idle              | Press insert money button |
| Money             | Insert money, Press select button, Cancel      |
| Product Selection | Select product, Cancel    |
| Product Dispense  | Dispence                  |


So based on the state of the system specific operations are allowed so we can use State design pattern


### State Design Pattern

```uml
@startuml

interface State {
	+ operation1()
    + operation2()
    + operation3()
}

class StateA {
	+ operation1()
    + operation3()
}

class StateB {
	+ operation3()
}

class StateC {
	+ operation2()
}

State <|.. StateA: is a
State <|.. StateB: is a
State <|.. StateC: is a


class Product {
	+ state: State
}

Product --> State: has a


@enduml
```


## Class Diagram

```UML
@startuml

interface State {
	+ clickOnInsertCoin(VendingMachine)
    + clickOnSelectItem(VendingMachine)
    + insertCoin(VendingMachine)
    + selectItem(VendingMachine)
    + getChange(VendingMachine)
    + getRefund(VendingMachine)
    + updateInventory(VendingMachine)
}

class IdleState {
	+ clickOnInsertCoin(VendingMachine)
}

class InsertMoneyState {
	+ insertCoin(VendingMachine)
    + getRefund(VendingMachine)
    + clickOnSelectItem(VendingMachine)
}

class SelectProductState {
	+ selectItem(VendingMachine)
    + getRefund(VendingMachine)
}

class DispenseProductState {
	+ updateInventory(VendingMachine)
}

State <|.. IdleState: is a
State <|.. InsertMoneyState: is a
State <|.. SelectProductState: is a
State <|.. DispenseProductState: is a

enum Coin {
	
}

class VendingMachine {
	- State state
    - List<Coin> coins
    - Inventory inventory
    + changeVendingMachineState(State)
}

enum ItemType {
	LAYS
    KURKURE
    PEPSI
    COKE
}
class Item {
	- ItemType type
	- int price
    ..getter and setter..
}

class ItemShelf {
	- Item item
    - int code
    ..getter and setter..
}

class Inventory {
	- List<ItemShelf> items
}

VendingMachine --> State: has a
VendingMachine --> Inventory: has a
VendingMachine -> Coin: has

Inventory --> ItemShelf: has

ItemShelf --> Item: has a
Item -> ItemType: has a



@enduml
```


