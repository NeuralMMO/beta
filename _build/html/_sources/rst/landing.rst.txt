.. |icon| image:: /resource/icon.png

.. role:: python(code)
    :language: python

.. figure:: /resource/poster.png

.. grid:: 3

    .. grid-item-card::  Github
      :link: https://github.com/neuralmmo

      Neural MMO is free and open-source software

    .. grid-item-card::  Discord
      :link: https://discord.gg/BkMmFUC

      Join our community for support and discussion

    .. grid-item-card::  Competition
      :link: https://www.aicrowd.com/search?utf8=%E2%9C%93&q=neural+mmo

      Compete for $20,000 in prizes at NeurIPS 2023
            
.. grid:: 3

    .. grid-item-card::  Baselines
      :link: https://wandb.ai/jsuarez/NeuralMMO/reportlist

      Baselines and results on WandB

    .. grid-item-card::  Paper
      :link: https://datasets-benchmarks-proceedings.neurips.cc/paper/2021/hash/44f683a84163b3523afe57c2e008bc8c-Abstract-round1.html

      Read our NeurIPS 2021 paper

    .. grid-item-card::  Twitter
      :link: https://twitter.com/jsuarez5341

      Follow the developer on Twitter

Neural MMO is a computationally accessible, open-source research platform designed to simulate populations of agents in virtual worlds. Your objective is to train a team of agents to complete tasks they have never seen before against opponents they have never seen before on maps they have never seen before. 

**2023 Competition:** Successfully complete the most tasks to win! At stake are $20,000 in prizes sponsored by Parametrix.ai. All submissions receive A100 compute credits for training sponsored by Stability.ai. 

.. dropdown:: Track Details

   NMMO has three tracks to compete and win. In all tracks, the objective is for Agent teams to accomplish tasks. Gameplay is over thousands of rounds, with increasing task and competitor difficulty. For the RL and Curriculum tracks, all entrants receive up to 8 hours of free A100 compute time per submission to train. For the No Holds Barred track, competitors bring on their own, non-limited compute power. This track is intended for larger labs and companies looking to push the boundaries 

   .. tab-set::

      .. tab-item:: Reinforcement Learning

         Train teams of agents using RL to complete tasks. Customize the RL algorithm, model, and reward structure, but leverage a fixed baseline curriculum of tasks for training.

         This is an opportunity for you RL enthusiasts to test your skills building agents that can survive and thrive in a massively multi-agent environment full of potential adversaries. Your task is to implement a *policy* that defines how your 8 Agent team performs within a novel environment. At the outset of each game, your team will receive a randomly generated task. Complete the task to score a point. We will evaluate submissions against each other over thousands of games. Whoever scores the most points wins.

         The RL track includes control over the RL algorithm, environment rewards signal, observation featurization, and the neural network architecture. The presentation and sampling of tasks are provided by the baseline and are treated as constants. All RL agent teams are trained on the same baseline task curriculum. While hybrid methods are allowed, with the new emphasis on tasks, it is unlikely that pure traditional scripting will be effective.

      .. tab-item:: Curriculum Generation

         The Curriculum track is a great way for programmers to compete and participate, without the need for advanced knowledge of AI. In this track, you will design unique and useful curricula for training successful teams on tasks. A curriculum is a structured set of tasks presented to the RL algorithm intelligently to maximize learning. Design the task generator, task sampler, and reward using Python.

         All submitted curricula will be applied to the same baseline RL policy to control a team of agents. Your objective is to create a curriculum of tasks that results in better, more robust learning such that agents are able to complete tasks not seen during training. You will receive performance metrics to see how effective the curriculum is and iterate your training curriculum. The reinforcement learning algorithm, observation featurization, and neural network architecture are provided by the baseline and remain constant across teams.

        .. code-block:: python

            # Insert actual code here:
            metrics = train_on_tasks(tasks)
            metrics = evaluate_on_tasks(tasks)

            tasks = make_some_tasks()
            metrics = evaluate_on_tasks(tasks)

            if tasks_are_good:
               train_on_tasks(tasks)

         Once trained on your curriculum, your Agent team policy will compete to complete novel, held-out tasks in live competition across over a thousand rounds of increasing difficulty.For researchers and advanced users, we encourage approaches leveraging `ELM <https://arxiv.org/abs/2206.08896>`_ and provide a code generation model with the baselines.

      .. tab-item:: No Holds Barred

         Combine RL and curriculum approaches. Entrants provide their own compute to win via any way possible - just don't hack our servers!

         Deploy both RL and Curriculum approaches to create the ultimate 8 Agent team policy. All methods are open and no constraints on (self-provided) compute. Only restrictions are: no unauthorized modifications of the game or other submissions. 

.. dropdown:: Contributors

   **Joseph Suarez**: Creator and lead developer of Neural MMO.

   CarperAI team for NMMO 2.0:
    - **David Bloomin**: Rewrite of the engine for 2.0, port and development of the RL baseline
    - **Kyoung Whan Choe**: Rewrite of Neural MMO game code and logging for 2.0, contributions to the RL baseline and task system
    - **Hao Xiang Li**: Neural MMO 2.0 task system
    - **Ryan Sullivan**: Integration with Syllabus for the curriculum learning baseline
    - **Nishaanth Kanna**: Co-developer of the ELM curriculum baseline
    - **Daniel Scott**: Co-developer of the ELM curriculum baseline
    - **Rose S. Shuman**: Technical writing for this documentation site and for the competition
    - **Herbie Bradley**: Supervision of the curriculum generation baseline with OpenELM
    - **Louis Castricato**: Co-founder and team lead of Carper AI; supervisor of Carper AI development efforts.

   **Sara Earle**: Created 3D assets and 2D icons for items in NMMO 2.0. Hire her on UpWork if you like what you see here.

   Previous open source contributors, listed by time since latest contribution. Discord handle have been used for individuals who have not granted explicit permission to display their real names:
      - **Thomas Cloarec**: Developed the dynamic programming backend for scripted baseline agents
      - **Jack Garbus**: Major contributions to the logging framework, feedback on the documentation and tutorials
      - **@tdimeola**: Feedback on the documentation and tutorials
      - **@cehinson**: Mac build of the Unity3D client
      - **Yilun Du**: Assisted with experiments for 1.0 at OpenAI

.. dropdown:: BibTex Citation

   .. code-block:: text

      @inproceedings{nmmo_neurips,
         author = {Suarez, Joseph and Du, Yilun and Zhu, Clare and Mordatch, Igor and Isola, Phillip},
         booktitle = {Proceedings of the Neural Information Processing Systems Track on Datasets and Benchmarks},
         editor = {J. Vanschoren and S. Yeung},
         pages = {},
         title = {The Neural MMO Platform for Massively Multiagent Research},
         url = {https://datasets-benchmarks-proceedings.neurips.cc/paper/2021/file/44f683a84163b3523afe57c2e008bc8c-Paper-round1.pdf},
         volume = {1},
         year = {2021}
      }

.. tab-set::
   
   .. tab-item:: PufferTank

      Docker `container <https://github.com/PufferAI/PufferTank>`_ including Neural MMO and baselines. Guarantees correct dependencies and environment setup. Recommended for all users. Use the pip package if you really want a local setup.

      .. code-block:: text

        Install Docker Hub, VSCode, and the VSCode dev containers plugin.
        Clone PufferTank on Linux/MacOS/WSL
        VSCode: F1 -> "Remote-Containers: Open Folder in Container" -> Select PufferTank folder
        You now have a fully functional GPU dev environment.

   .. tab-item:: Pip Package

      Official support for Ubuntu 20.04/22.04, WSL, and MacOS

      .. code-block:: python

         # Quotes for mac compatibility.
         pip install "nmmo"
         
         # Clone baselines repository. Optional but recommended: setup WanDB integration.
         git clone https://github.com/neuralmmo/baselines
         echo YOUR_WANDB_API_KEY > baselines/wandb_api_key

         #Run training
         python -m tools.train

   .. tab-item:: Source

      Only recommended for developers of Neural MMO who can't run PufferTank.

      .. code-block:: python

         mkdir neural-mmo && cd neural-mmo

         git clone https://github.com/neuralmmo/environment
         git clone https://github.com/neuralmmo/baselines

         # WSL users: run this part on Windows. Client opens in Cocos2D.
         git clone https://github.com/neuralmmo/client
         
         echo YOUR_WANDB_API_KEY > baselines/wandb_api_key
         cd environment && pip install -e .

.. card::
   :img-background: /../_static/banner.png

|icon| About Neural MMO
#######################

Neural MMO is a computationally accessible, open-source research platform designed to simulate populations of agents in virtual worlds. Each instance of Neural MMO uses procedural generation algorithms to create unique landscapes, NPCs, and resources. The project is inspired by classic Massively Multiplayer Online Role-Playing Games (MMOs) - a genre defined by interaction with a large number of other players. NMMO stands for Neural MMO. It is a platform for creating intelligent agent that are typically parameterized by a neural network. 

In NMMO, Agents in teams must forage for resources to stay alive and to mine materials to increase their combat and task completion capabilities. Agents can level up their fighting styles and equipment, practice different professions, and engage in trade based on market demand. The world is also populated by non-player characters (NPCs) of varying friendliness. MMO settings allow player teams to interact in interesting ways and use entirely different strategies. 

Our goal is to support a broad base of multiagent research that would be impractical or impossible to conduct using other environments. Unlike other game genres typically used in research, MMOs simulate persistent worlds that support rich player interactions and a wider variety of progression strategies. These properties seem important to intelligence in the real world. An objective of this competition and platform is to spur research towards increasingly general and cognitively realistic environments. 

.. code-block:: python

   from nmmo import Env

   # Default environment. Keep reading for config options
   env = Env(config=None)
   obs = env.reset()

   while True:
      actions = {} # Compute with your model
      obs, rewards, dones, infos = env.step(actions)

Environments provide a standard PettingZoo API. Join our community Discord and post in #support for help (do not raise Github issues for support). See the cards at the top of this page for source code, baselines, latest publications, social media, and news!

.. dropdown:: General features of NMMO

  - **Terrain:** Procedurally generated maps with obstacles
  - **Resource:** Agents must forage for resources to survive
  - **Combat:** Agent can fight each other
  - **NPC:** Maps are inhabited by mobs of varying friendliness
  - **Progression:** Agents improve various abilities through usage
  - **Item:** Agents can acquire a number of items with distinct uses
  - **Equipment:** Agents can use armor, weapons, and tools
  - **Profession:** Agents can practice distinct jobs
  - **Exchange:** Agents can trade items on a global market

.. dropdown:: General features of NMMO

  - Gameplay is on a map
  - Map has Water, Stone, and Grass tiles in a 128 x 128 array
  - A team has 8 Agents
  - There are 7 other teams competing in each round, each with 8 Agents as well
  - Map is also populated by Non-Playable Characters (NPCs) of varying hostility
  - Agents survive if they have HP
  - Goal is to complete tasks

|icon| Your Objective
#####################

You control a team of 8 agents. The ultimate goal is to score more points by completing more challenge tasks across the 1024 games than all other teams in that round. Agents must collect food and water to survive and have 8 individual professions that help them collect resources. Resources can be used to create consumable items that restore food, water and heath as well as to create ammunition that increases damage in combat. Higher level resources create better consumables and ammunition. Agents may aquire armor to protect themselves in combat and weapons to increase their damage output. Agents can also trade items on a global market. Combat is turn based and Agents can attack each other using one of three styles: Melee, Range, and Magic. Agents can level up their skills in each style and in each profession. The world is populated by NPCs that can be defeated to obtain items and increase power.

**In NMMO, Agent teams that complete the most assigned tasks win.** There are 128 Agents in play at the start of a game round, making 16 teams of 8. Everyone plays at least 1000 rounds of the game, with assorted opponent teams assigned based on a matchmaking algorithm which optimizes for opponent teams of similar skill level. In case of ties, ranking scores look at how many of your Agents survived to the end, and how healthy they were then. 

|icon| Wiki Content
###################

**What do Agents Do?**

Your team of 8 Agents:
  - Use resources to increase Food, Water, and HP levels.
  - Collect resources to make ammunition 
  - Use ammunition to increase weapon power. You do more damage if you have ammo; ammo has levels; higher level ammo does more damage than lower. 
  - Wear armor to protect themselves in combat
  - Defend or attack enemy Agents in combat using one of three styles (Range, Melee, Magic)
  - Buy and sell tools, consumables, armors, ammunitions, and weapons
  - Level up in all categories to increase power
  - Specialize in Professions, also known as skills. Each Agent has 8 and can level them all up. However, it’s not possible in the game to maximize all due to time limits. As such, what to max is a question of strategy. Different Agents on the same team can specialize in different Professions. 
  - Kill both NPC and enemy agents to gain items and increase score
  - Die when they run out of HP

**In NMMO, Agent teams that complete the most assigned tasks win.**

There are 128 Agents at play at the start of a game round, making 16 teams of 8. Everyone plays at least 1000 rounds of the game, with assorted opponent teams assigned based on a matchmaking algorithm which optimizes for opponent teams of similar skill level. 

In case of ties, ranking scores look at how many of your Agents survived to the end, and how healthy they were then. 

.. dropdown:: About Levels and XP

**Agents**
 - Levels range from 1 to 10
 - Agents spawn with all skills at level 1 (0 XP)
 - Level x+1 requires 10*2^x* XP

 - Agents are awarded 1 XP per attack

 - Agents are awarded 1 XP per ammunition resource gathered
 - Agents are awarded 5 XP per consumable resource gathered
 
 - All items except gold will appear in varying levels
  
**Items and Equipment**
 - All items appear in level 1-10 variants. 
 - Agents can equip armor up to the level of their highest skill
 - Agents can equip weapons up to the level of the associated skill
 - Agents can equip ammunition and tools up to the level of the associated skill


Keeping Agents Alive
********************

Agents stay alive by:
  - Eating food
  - Drinking water
  - Protecting HP in combat

**Tile Spaces**

Each environment contains an automatically generated tile-based game map of 128 x 128 tiles. Tiles come in three types:
  - Water (resource for water; for movement is an **obstacle**)
  - Stone (resource for battle performance in Mellee and Magic styles; for movement is an **obstacle**)
  - Grass (resource for food, HP, and battle performance in range style; for movement is **passable**)

Agents have food / water bars starting on 100

Walk on food tile - regain full food. Tile disappears. Will respawn later, at a random time and same place. 
If you adjacent to water tile - regain full water. Done.
Skills - prospecting, carving, alchemy - walk on resource tile. Get the resource. Will respawn later, same place. Will be a different quality/level of resource, depending on Agent levels/tools.

.. dropdown:: About the tile generation algorithm
    
    The default tile generation algorithm is more sophisticated than typical Perlin noise -- it stretches the space of one Perlin fractal using a second Perlin fractal. It further attempts to scale spacial frequency to be higher at the edges of the map and lower at the center. This effect is not noticable in small maps but creates large deviations in local terrain structure in larger maps.
    
About HP
********

If not taking damage, not hungry/thirsty will slowly regain HP
Food/Water levels go down each time tick. 
Scales: Lose 5 Food and 5 Water per game tick. Start with 100.
Lose 10 HP per tick if out of food. Lose 10 HP per tick if out of water. Lose 20 HP per tick if out of both food and water.
If above half food and half water, regain 10 HP per tick

About Combat
************

Combat - is parrying back and forth, one attack per tick. Taking turns. Damage is a randomized function of confluence of factors. Include: Fighting style; combat skill level; weapon level; armor levels. 

Agents select from Melee, Range, and Mage style attacks. These obey a rock-paper-scissors dominance relationship: 
Melee beats Range beats Mage beats Melee. 
Dominance is calculated using the attacker's chosen attack skill and the defender's main combat skill.

The attacker always has an advantage in that they can select the skill strong against the target's main skill. However, the defender can immediately retaliate in the same manner. Additionally, a combat style in which an agent has a higher level and better equipment may outperform one with only the effectiveness multiplier.

Armor requires at least one skill greater than or equal to the item level to equip. Armor provides defense that increases with equipment level.
Weapons require an associated fighting style skill level greater than or equal to the item level to equip. Weapons boost attacks; boost is enhanced by weapon level.
Tools grant a flat defense regardless of item level.

Observation Space
*****************

Each agent observes a groups of entities comprising nearby tiles and agents, its own inventory, and the market. Continuous and discrete tensors of attributes parametrize each entity group. An extra variable *N* counts the number of entities per group.

.. code-block:: python
  :caption: Observation space of a single agent

  observation_space(agent_id) = {
        'AgentId': Discrete(1),
        'Entity' :Box(-1048576.0, 1048576.0, (100, 22), float32),
        'Inventory': Box(-1048576.0, 1048576.0, (12, 16), float32),
        'Market': Box(-1048576.0, 1048576.0, (640, 16), float32),
        'Tick': Box(-1048576.0, 1048576.0, (1, 1), float32),
        'Tile': Box(-1048576.0, 1048576.0, (225, 3), float32)
    }

Attack range is 3 tiles. 
Visible tile range is 7 tiles.
View is full sweep:

**Also, multiple enemy Agents can attack you in a given tick, while you can only attack one enemy in a tick. 

.. code-block:: python

   def COMBAT_DAMAGE_FORMULA(self, offense, defense, multiplier):
      '''Damage formula'''
      return int(multiplier * (offense * (15 / (15 + defense))))

Start:
You: 100 HP, bad armor and weapons
Them: 75 HP, good armor and weapons


Tick 1:
You attack them. They lose 28 HP
They attack you. You lose 37 HP


Tick 2:
You attack them. They lose 24 HP
They attack you. You lose 42 HP


Tick 1: 
You attack them. They lose 28 HP
They run


Tick 2: You attack them. They lose 25 HP.
They consume a poultice to regain 50 HP and run


This continues for some time
You give up


About Professions
*****************

There are 8 Professions that Agents can learn and level up in. Agents can improve their skills in multiple Professions, but will not be able to progress in all Professions. As such, how Professions are distributed across Agent teams is a part of game strategy. 

Agents have an inventory that can hold 12 items.

+----------------+-------------+---------+-----------------+------------+------------------+------------------+
| Type           | Profession  | Tool    | Level up method | HP Effect  | Food/Water Level | Market Buy/Sell  |
+================+=============+=========+=================+============+==================+==================+
|                | Mage        | Wand    | Hitting and     | \-HP level |                  | Wand             |
|                +-------------+---------+ damaging        | unless you |                  +------------------+
| Combat         | Melee       | Sword   | NPCs and        | take no    |                  | Sword            |
|                +-------------+---------+ Enemies         | damage     |                  +------------------+
|                | Range       | Bow     |                 |            |                  | Bow              |
+----------------+-------------+---------+-----------------+------------+------------------+------------------+
|                | Fishing     | Rod     | Level up via    | \+HP level | \+Food &         | Fish Ration      |
| Gathering      +-------------+---------+ experience      +------------+ Water level      +------------------+
|                | Herbalism   | Gloves  | and use         | \+HP level |                  | Poultice         |
+----------------+-------------+---------+-----------------+------------+------------------+------------------+
|                | Carving     | Chisel  |                 | \+HP level |                  | Chisel & Shaving |
|                +-------------+---------+                 +------------+                  +------------------+
|                | Prospecting | Pickaxe |                 | \+HP level |                  | Pickaxe & Scrap  |
|                +-------------+---------+                 +------------+                  +------------------+
|                | Alchemy     | Arcane  |                 |            |                  | Arcane & Shards  |
+----------------+-------------+---------+-----------------+------------+------------------+------------------+

Tools
*****
All Tools provide a flat 30 defense regardless of item level.
Tools need a pertinent skill level (fishing, herbalism, prospecting, carving, alchemy) > or = the item level to equip.
Tools enable an agent to collect an associated resource (ration, poultice, scrap, shaving, shard) at a level equal to the item level.

Rations
*******
Consume to restore 5 food and water per item level.
Requires at least one skill greater than or equal to the item level to use.

Poultices
*********
Consume to restore 5 health per item level.
Requires at least one skill greater than or equal to the item level to use.


Competition Environment 
***********************

Agents on Tiles
***************

At the start of a game, all Agents on all teams spawn together around the perimeter of the map on the same tile. Agent teams are evenly dispersed around the perimeter. 


**NPCs are scattered across the entire map. They get stronger and more aggressive towards the center. NPCs are all individuals; they fight each other as well; and they are all controlled by very basic scripts. Their aggression and strength levels are correlated, but otherwise are identical. 

Agents can occupy the same tile as other Agents. Other Agents can be their own teammates and/or other team’s Agents. **Is there a limit to number or type of Agents on a single tile? No LIMIT Also, can NPCs be on the Tile and treated the same as player Agents? YES

**Time and Gameplay**
The gameplay consists of time units called “ticks.” Each tick provides the opportunity for every Agent and NPC** to do any, all or none of the following actions:
   
   - Move **1 tile in any available direction.**
      - Agents cannot move off of the game space, or **into water.** 
      - As the game progresses, the action space becomes constrained as a fog encircles the board. Agents cannot be in tiles covered in fog, and all gradually move towards the center of the game space.
  
  - Attack an Agent - either NPC or from another team.
      - Attack can only be against one other Agent or NPC
      - To attack, your Agent must be within three tiles as the opponent -- actually within a 7x7 square around your Agent.**
   
   - Buy OR Sell
      - **explanation of market system**
  
  - Give an Item to a Teammate
      - Giving items to other Agents is not permitted
   
   - Remove an Item from Inventory
      - *Reasons to sell an item - 
         - Item has no gameplay utility at that juncture, including no market value
         - Item would take too long to sell, and opportunity cost of space being occupied in inventory is higher
         - Inventory capacity is 12 items, including armor, weapon, tools, and consumables.

**TBD - whether one can Buy/Sell; Give and Destroy simultaneously

**Tile Resources**
On these tiles are various important resources. Access resources and stay alive in the game - EAT, DRINK and COMBAT.
There is a 2.5 percent chance to obtain a weapon while gathering ammunition on a tile.

**TODO: Port table**

**Market: Buy and Sell Resources**

Gold is the currency for buying and selling goods in NMMO. Gold comes in full units, and cannot be sub-divided. Gold is acquired by selling items, and used for buying items.

Prices are set by **Explain market pricing here
Agents set their own prices and receive gold when someone is willing to accept their price. Within the same team, can gift to one another. 

##Line 400 and 421 on gifting in teams contradict. Which is correct? If teammates can gift - is it only if on the same tile?

 - Agents place sell offers on the market for one of their items at a desired price
 - The item is immediately removed from the seller's inventory
 - Other agents can immediately buy that item and receive it
 - If multiple agents attempt to buy the same item at the same time, the market will attempt to fulfill the request from another seller at a price no more than 10% higher.

Agents only observe the current best offer for each item of each level. This bounds the observation and action spaces.

**TODO**

Each agent may take multiple actions per tick -- one from each category. Each action accepts arguments.

.. code-block:: python
  :caption: Action space of a single agent

  action_space(agent_idx) = {
      nmmo.action.Move: {
          nmmo.action.Direction: {
              nmmo.action.North,
              nmmo.action.South,
              nmmo.action.East,
              nmmo.action.West,
          },
      },
      nmmo.action.Attack: {
          nmmo.action.Style: {
              nmmo.action.Melee,
              nmmo.action.Range,
              nmmo.action.Mage,
          },
          nmmo.action.Target: {
              Entity Pointer,
          }
      },
      nmmo.action.Use: {
          nmmo.action.Item: {
              Inventory Pointer,
          },
      },
      nmmo.action.Sell: {
          nmmo.action.Item: {
              Inventory Pointer,
          },
          nmmo.action.Price: {
              Discrete Value,
          },
      },
      nmmo.action.Buy: {
          nmmo.action.Item: {
              Market Pointer,
          },
      },
      nmmo.action.Comm: {
          nmmo.action.Token: {
              Discrete Value,
          },
      },
  }

Pointer actions refer to a selection from the observation space. For example, to purchase an item, an agent should select the corresponding item from the observation space. This works by computing a similarity score against entity embeddings and is handled by the baseline model.

|icon| NPCs
************

**Characteristics**
 - NPCs are controlled by one of three scripted AIs
 - Passive NPCs wander randomly and cannot attack
 - Neutral NPCs wander randomly but will attack aggressors and give chase using a Dijkstra's algorithm based pathing routine
 - Hostile NPCs will actively hunt down and attack other NPCs and players using the same pathing algorithm
 - NPCs will appear in varying levels

**NPC Items**
 - NPCs spawn with random armor piece
 - NPCs spawn with a random tool
 - Any equipment dropped will be of level equal to the NPC's level
 - NPCs spawn with gold equal to their level

Generally, Passive NPCs will spawn towards the edges of the map, Hostile NPCs spawn in the middle, and Neutral NPCs spawn somewhere between.

|icon| Tasks
************

**In process**

**About Tasks**
- Goal is to accomplish specific tasks from the curriculum for points. Tasks are randomly generated and assigned at the beginning of each round. If a Team accomplishes a Task, they receive 1 point for the round. 
- Each team receives different tasks from one another each round.
- Difficulty of the tasks evens out, as all teams compete with each other 1024 rounds to determine the best teams overall in that group.
- Based on the average scores, teams are placed in the next round of 1024 with other teams whose performance matches their own.


Task = objective needed to complete within the game. In a game round, tasks are concatenated based on AND, OR, or NOT. Probably Maximum of 5 subtasks in a given challenge task, maybe more commonly 3 subtasks.

Inflict(damage_type, quantity) - 
Damage_type = 3 combat styles 
Quantity = 1-100 HP out of total 100 HP
Ex. Inflict 5 damage with melee

Defeat(npc/player, level)
npc/player = NPC or Player, Unit = 1
Level = 1-10
Defeat a level 5 npc

Achieve(skill, level)
Skill = 8 skills (Professions)
Level = 10
Ex: Achieve level 5 prospecting

Harvest(resource, level)
Resource = 5 resources
Level = 10 levels
Ex: collect a level 3 shard

Equip(type, level)
Type = Hat, Top, Bottom
Level = 10
Ex: equip a level 5 hat

Hoard(gold) - Accumulate a total of 20 gold as a team
Gold: Units of transaction ingots

Group(num_tiles, num_teammates) - Always stay within 5 tiles of at least 3 of your teammates
Num_tiles: Variable starting with tile you’re as 0
Num_teammates: Self evident. Stay together-ish

Spread(num_tiles, num_teammates) - Always stay at least 5 tiles away from at least 3 of your teammates
Opposite of Group

Defend(teammate) - Don’t let your 3rd teammate die
Teammate: Specific member of your team can’t die

Eliminate(team, direction) - Eliminate the team that spawns to your right
Team: ID # of team
Direction: Left; Right