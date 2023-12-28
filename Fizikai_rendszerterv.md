# Fizikai rendszerterv:

## 3NF Adatbázis Terv:
```
@startuml

object Automata

Automata : AutomataId 
Automata : Gyári Szám
Automata : Hely leírás
Automata : Utolsó Feltöltés Dátuma


Automata --|> Eladott_Kávé

object Eladott_Kávé {
AutomatId 
Kávé
Hosszú Kávé
Tej 
Cukor
Haszon
}
@enduml
```
