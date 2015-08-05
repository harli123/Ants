# Ants
Ants Project - run using the "ants_gui.py" file for graphical version, can run using "ants.py" but it will just be a text based version of the game

versions of gameplay:
--help      Prints this help message
--ten       Start with ten food
--full      Loads a full layout and assault plan
--water     Loads a full layout with water
--insane    Loads a difficult assault plan

Ants project from CS61A (3rd project). Only code done by me is found in "Ants.py" file and is tagged between "HLI" comments. Need to download image folder from: (until I can fully use github directly, github windows not installing therefore harder for me to drop in other type of files)

http://www-inst.eecs.berkeley.edu/~cs61a/sp14/proj/ants/ants.html


General flow of game:
- Food is required to make ants
- Bees come into the "tunnel" from their "hive". You lose if (1)any bee gets through to the other side of the tunnel or (2) if the bee goes onto the same "tunnel tile" as the placed "queen-ant"
- Time denotes the turns that have elasped for the current game. Whenever time increases that means a turn has been taken
- Each turn the ants and bees take an action. Bees (1) fly or (2) sting - unless affected by the slow / stun ants. Each ant does a specific action noted below

- General Rules:
  - Can only place ants on "tunnel tiles" 
  - Ants cannot be placed on water tiles (bees can fly through them)
  - Only one ant per tile (bodyguard ant has special ability to override this) (there can be multiple bees on a tile)
  - Numbers below ant images are their food cost
  - Bees cannot move past a "tunnel tile" until the ant(s) on it have been killed
  - Can build ants on tiles that already have bees on them
  - All units have (1) armor rating (2) damage rating. Armor denotes how many times they can be hit before dying and damage denotes by how much they reduce their target's armor

- Different Ant Abilities (from left to right on how they appear in the GUI)
  - All ants default to armor = 1 and damage = 1 unless otherwise denoted below
  - Harvester Ant : Damage = 0 Each turn adds one food to your "colony"
  - BodyGuard Ant: Armor = 4. Damage = 0 Can have one bodyguard ant and another type of ant on the same tile (order of placement on tile between ant type is irrelevant). Note: cannot have 2 bodyguards or more than 2 ants on a tile. They get attacked by bee first, bee doesn't start to attack other ant on tile until bodyguard ant has been killed
  - Hungry Ant: Damage = total armor value of target bee. Kills bee in one turn but then is inactive for 3 turns
  - Ninja Ant: Is not "seen" by bees. Does one damage to all bees on same tile. Bees' movement are not impeded by Ninja ant so only stay on same tile for a turn, if Ninja Ant is only ant. Bee doesn't attack Ninja Ant
  - Wall Ant: Armor = 4, Damage = 0. Does nothing but have a higher armor value
  - "Bye" button - allows user to remove ant that has already been placed in a tile. Cannot remove queen ant
  - Fire Ant: Damage = 3 when killed. When killed "explodes" and deals damage to all bees on same tile
  - Long Thrower Ant: Throws leaf at random bee on closest tile within range. Can only hit bees that are no closer than 3 tiles to the ant. No restriction on max distance
  - Short Thrower Ant: Throws leaf at random bee on closest tile within range. Only hits bees that are no more than 2 tiles in front of it (includes the same tile)
  - Stun Ant: Damage = 0. Causes a single bee to not act for 2 turns
  - Slow Ant: Damage = 0. Causes a single bee to not act if "time" is odd for a single turn
  - Scuba Ant: Can be placed in water tiles. Throws leaves, no min or max restrictions
  - Queen Ant: Can be place in water tiles, if bee is on same tile, even if there is a bodyguard ant there as well, you lose. Cannot be removed by "bye" button. Doubles all ants' damage, not including itself, in the same "tunnel". On top of doubling effect has same scuba ant attack

