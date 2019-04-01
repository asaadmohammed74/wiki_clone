This packet is sent from the game server to the game client in newer client versions when the user views the equipment of any player (including themselves). It is used to display all of the characters attributes.

### Patch 5517

| Offset | Type | Description | Example |
| -------- | -------- | -------- | -------- |
| 0 | UInt16 | Length | 32 |
| 2 | UInt16 | Type | 2071 |
| 4 | UInt32 | Target Identity | 1000000 |
| 8 | UInt32 | Life | 100 |
| 12 | UInt32 | Mana | 1000 |
| 16 | UInt32 | MaximumAttack | 1000 |
| 20 | UInt32 | MinimumAttack | 1000 |
| 24 | UInt32 | Defense | 1000 |
| 28 | UInt32 | MagicAttack | 1000 |
| 32 | UInt32 | MagicDefense | 100 |
| 36 | UInt32 | DodgePercent | 92 |
| 40 | UInt32 | Agility | 20 |
| 44 | UInt32 | Hit Rate | 20 |
| 48 | UInt32 | BonusAttackPercent | 20 |
| 52 | UInt32 | BonusMagicPercent | 20 |
| 56 | UInt32 | ReduceDamagePercent | 20 |
| 60 | UInt32 | Unknown60 | 20 |
| 64 | UInt32 | BlessPercent | 20 |
| 68 | UInt32 | CriticalStrikePercent | 20 |
| 72 | UInt32 | SkillCriticalStrikePercent | 20 |
| 76 | UInt32 | ImmunityPercent | 20 |
| 80 | UInt32 | PenetrationPercent | 20 |
| 84 | UInt32 | BlockPercent | 20 |
| 88 | UInt32 | BreakthroughPercent | 20 |
| 92 | UInt32 | CounteractionPercent | 20 |
| 96 | UInt32 | DetoxicationPercent | 20 |
| 100 | UInt32 | DetoxicationPercent | 20 |
| 104 | UInt32 | FinalAttack | 20 |
| 108 | UInt32 | FinalMagicAttack | 20 |
| 112 | UInt32 | FinalDefense | 20 |
| 116 | UInt32 | FinalMagicDefense | 20 |
| 120 | UInt32 | MetalResistPercent | 20 |
| 124 | UInt32 | WoodResistPercent | 20 |
| 128 | UInt32 | WaterResistPercent | 20 |
| 132 | UInt32 | FireResistPercent | 20 |
| 136 | UInt32 | EarthResistPercent | 20 |
