# Követelmény specifikáció:

## Bevezetés:

A projekt célja létrehozni egy olyan kávé autómatát, amelyből lehet kávét vásárolni különböző opciókkal.
Fontos, hogy az automata jelezze, hogy mikor kell újra feltölteni, és hogy miből mennyit adott el, és ezzel milyen hasznot szerzett.

## Követelmény lista: 
| id | Követelmény                               | Leírás                                                                                                    |
|----|--------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| 1  | Elfogadható érmék                           | 20, 50, 100, és 200 Forintos érméket kell elfogadnia az automatának.                                       |
| 2  | Érmék visszadobása            | Gombnyomásra az automata vissza kell adja a bedobott érméket.                                            |
| 3  | Pénz ellenőrzése | Az automata csak akkor adhatja ki a kávét, ha elegendő pénz lett bedobva.                                   |
| 4  | Pontos visszajáró                           | A vásárlás végén az automata pontosan vissza kell adjon a felhasználónak a megfelelő visszajárást.           |
| 5  | Készlet jelzése                             | Az automata jeleznie kell a szolgáltató cég felé, ha a készlete a maximum készlet 30%-a alá csökken.       |
| 6  | Haszon számítása                            | Az automata képesnek kell lennie kiszámolni az eladott kávén szerzett hasznot.                             |

## Use Case:

```
@startuml
skinparam actorStyle awesome
actor Felhasználó as user

user --> (automata)
automata --> (penz)
penz --> (kave)
penz --> (vissz)
kave --> (vissz)

"Kávé automata" as (automata)
"Kávé vásárlás" as (kave)
"Pénz bedobás" as (penz)
"Visszajáró kérés" as (vissz)
@enduml
```
