# Quake2
Диаграмма классов для Quake II
# Quake II Class Diagram

```mermaid
classDiagram
    class Game {
        +start()
        +pause()
        +end()
    }

    class Level {
        +int number
        +String name
        +load()
        +restart()
    }

    class Player {
        +String name
        +int health
        +int armor
        +Weapon equippedWeapon
        +List~Item~ inventory
        +move(int x, int y, int z)
        +attack()
        +takeDamage(int amount)
    }

    class Enemy {
        +String type
        +int health
        +int damage
        +move()
        +attack(Player target)
        +takeDamage(int amount)
    }

    class Weapon {
        +String name
        +int damage
        +int ammo
        +reload()
        +fire()
    }

    class Item {
        +String name
        +String effect
        +use(Player player)
    }

    Game --> Level
    Level --> Player
    Level --> Enemy
    Player --> Weapon
    Player --> Item
    Enemy --> Weapon
