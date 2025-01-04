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

    class Character {
        +String name
        +int health
        +int armor
        +move(int x, int y, int z)
        +takeDamage(int amount)
    }

    class Player {
        +Weapon equippedWeapon
        +List~Item~ inventory
        +attack()
        +useItem(Item item)
    }

    class Enemy {
        +String type
        +int damage
        +attack(Character target)
    }

    class BossEnemy {
        +String specialAttack
        +performSpecialAttack(Character target)
    }

    class Weapon {
        +String name
        +int damage
        +int ammo
        +reload()
        +fire()
    }

    class MeleeWeapon {
        +int range
        +swing()
    }

    class RangedWeapon {
        +int range
        +aim()
    }

    class Item {
        +String name
        +String effect
        +use(Character character)
    }

    Game --> Level
    Level --> Character
    Character <|-- Player
    Character <|-- Enemy
    Enemy <|-- BossEnemy
    Player --> Weapon
    Player --> Item
    Weapon <|-- MeleeWeapon
    Weapon <|-- RangedWeapon

