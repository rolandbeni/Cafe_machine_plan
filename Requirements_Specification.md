# Követelmény specifikáció:

## Bevezetés:

A projekt célja létrehozni egy olyan kávé autómatát, amelyből lehet kávét vásárolni különböző opciókkal.
Fontos, hogy az automata jelezze, hogy mikor kell újra feltölteni, és hogy miből mennyit adott el, és ezzel milyen hasznot szerzett.

## Követelmények: 
Az autómatának tundnia kell, 20, 50, 100, és 200 forintos érméket elfogadni, és gombnyomásra az érméket visszadobni.
Csak akkor adhatja ki a kávét, ha már elegendő pénz be lett dobva, és a vásárlás végén visszaadni pontosan a visszajárót.
Az automatának jeleznie kell a szolgáltató cég felé, ha a készlet a teljes készlet 30%-a alá esett.
Fontos, hogy az eladott kávén szerzett hasznot is ki tudja számítani.

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
