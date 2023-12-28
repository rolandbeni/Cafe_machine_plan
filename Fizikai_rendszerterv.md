# Fizikai rendszerterv:

## 3NF Adatbázis Terv:
```
@startuml

object Automata

Automata : AutomataId 
Automata : Gyári Szám
Automata : Hely leírás
Automata : Utolsó Feltöltés Dátuma


Automata --|> Eladott_Kávé: 1:1

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
## Osztálydiagramm:
```
@startuml

class Kaveautomata {
  + kaveVasarlas(tipus: str, penz: int): bool
  + visszajaroKerese(): int
  + jelzesKuldese(): void
  + getHaszon(): int
}

Kaveautomata -- Kave

class Kave {
  - tipus: str
  - ar: int
}

@enduml
```
## Állapotgép: 
```
@startuml

state FeltoltesAlatt{
  [*] --> FeltoltesVege
  FeltoltesVege--> Uzemkesz
}

state Uzemkesz {
  [*] --> Kivalasztas
  Kivalasztas --> PenzEllenorzes
  PenzEllenorzes -->  KaveKeszites
  KaveKeszites -->  KaveKiadas
  KaveKiadas --> VisszajaroKiadas
  VisszajaroKiadas --> Kivalasztas
  Kivalasztas -->  JelzesKuldese
  JelzesKuldese-->  FeltoltesAlatt
  
}

@enduml
```
## Kommunikációs API Leírás:

- **Vásárlás API:**
  - POST /vasarlas
    - Input: {AutomataID, Kave, tej, cukor}
    - Output: {Siker, Visszajaro}

- **Készlet API:**
  - GET /keszlet/{AutomataID}
    - Output: { KaveMennyiseg, TejMennyiseg, CukorMennyiseg }

- **Haszon Lekérdezés API:**
  - GET /haszon
    - Output: { OsszHaszon }

