.. |icon| image:: /resource/icon.png

.. role:: python(code)
    :language: python

.. figure:: /resource/banner.png

|

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

|icon| NeurIPS 2023 NMMO Competition
####################################

Your objective is to train a team of agents to complete tasks they have never seen before against opponents they have never seen before on maps they have never seen before. 

Successfully complete the most tasks to win! 
At stake are $20,000 in prizes sponsored by Parametrix.ai.
All submissions receive A100 compute credits for training sponsored by Stability.ai. 

.. dropdown:: Track Details

   NMMO has Three Tracks to Compete and Win. In all tracks, the objective is for Agent teams to accomplish tasks. Gameplay is over thousands of rounds, with increasing task and competitor difficulty. For the RL and Curriculum tracks, all entrants receive up to 8 hours of free A100 compute time per submission to train. For No Holds Barred, competitors bring on their own, non-limited compute power.

   .. tab-set::

      .. tab-item:: Reinforcement Learning

         Train teams of agents using RL to complete tasks. Customize the RL algorithm, model, and reward structure, but leverage a fixed baseline curriculum of tasks for training.

         This is an opportunity for RL enthusiasts to test your skills building agents that can survive and thrive in a massively multi-agent environment full of potential adversaries. Your task is to implement an RL learned policy that defines how your 8 Agent team performs within a novel environment. At the outset of each game, your team will receive a random, generated task. Completing the task scores points. The winner scores the most points across thousands of game rounds.  

         Reinforcement Learning track includes control over the RL algorithm, environment rewards signal, observation featurization, and the neural network architecture. The presentation and sampling of tasks are provided by the baseline and are treated as constants. All RL Agent Teams are trained on the same baseline task curriculum. While hybrid methods are allowed, with the new emphasis on tasks, it is unlikely that pure traditional scripting will be effective.

      .. tab-item:: Curriculum Generation

         Design unique and useful curricula for training successful teams on tasks. RL experience is not required. Design the task generator, task sampler, and reward using Python. NMMO particularly encourages approaches leveraging ELM (link) and provides a code generation model with the baselines.

         The Curriculum track is a great way for coders to compete and participate, without the need for RL or AI/ML! Link to Curriculum Track.

         All curriculum developers are paired with identical baseline policy RL Agent teams. Your objective is to create a curriculum of tasks for the Agent team to evaluate or train on. You will receive performance metrics to see how effective the curriculum is and iterate your training curriculum. The reinforcement learning algorithm, observation featurization, and neural network architecture are provided by the baseline and remain constant across teams.

         Once trained on your curriculum, your Agent team policy will compete to complete novel, held-out tasks in live competition across over a thousand rounds of increasing difficulty. 

         .. code-block:: python

            # Insert actual code here:
            metrics = train_on_tasks(tasks)
            metrics = evaluate_on_tasks(tasks)

            tasks = make_some_tasks()
            metrics = evaluate_on_tasks(tasks)

            if tasks_are_good:
               train_on_tasks(tasks)

      .. tab-item:: No Holds Barred

         Combine RL and curriculum approaches. Entrants provide their own compute to win via any way possible - except hacking NMMO’s servers!

         Deploy both RL and Curriculum approaches to create the ultimate 8 Agent team policy. All methods are open and no constraints on (self-provided) compute. Only restrictions are: no hacking or unauthorized modifications of the game or other submissions. 

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
   
   .. tab-item:: Pip Package

      .. code-block:: python
         :caption: Packaged installation. Officially supports Ubuntu 20.04/22.04, WSL, and MacOS. Tested with Anaconda Python 3.9
         
         # Install NMMO with baseline dependencies (quotes for mac compatibility).
         pip install "nmmo[cleanrl]"
         
         # Clone baselines repository. Optional but recommended: setup WanDB integration.
         git clone https://github.com/neuralmmo/baselines nmmo-baselines
         echo YOUR_WANDB_API_KEY > nmmo-baselines/wandb_api_key

         #Run a quick demo (download client below)
         python -m demos.minimal

   .. tab-item:: Source

      Download the latest client `here <https://github.com/neuralmmo/client/releases>`_ (WSL users: do this on your Windows host). Start the demo and run the executable for your platform in client/UnityClient/. After a few seconds, the demo console will show a connection message and the client will load the map. The on-screen instructions demonstrate how to pan and zoom. You can also click on agents to examine their skill levels. The in-game console (which you can toggle with tab) gives you access to a number of overlay visualiztions.

      .. code-block:: python
         :caption: Setup from source for developers (slow without --depth=1)

         mkdir neural-mmo && cd neural-mmo

         git clone https://github.com/neuralmmo/environment
         git clone https://github.com/neuralmmo/baselines
         git clone https://github.com/neuralmmo/client
         
         echo YOUR_WANDB_API_KEY > baselines/wandb_api_key
         cd environment && pip install -e .[all]


|icon| About NMMO
#################

Neural MMO is an open-source research platform that is computationally accessible. It enables populations of agents to be simulated in procedurally generated virtual worlds. A procedurally-generated world uses algorithms to generate unique landscapes, NPCs, and resources that change each round.

NMMO is inspired by classic Massively Multiplayer Online Role-Playing Games. An MMO can be any online video game in which a player interacts with a large number of other players. NMMO stands for Neural MMO. It is a platform for intelligent agent creation, which are typically parameterized by a neural network. 

In NMMO, Agents in teams must forage for resources to stay alive and to mine materials to increase their combat and task completion capabilities. Agents can level up their fighting styles and equipment, practice different professions, and engage in trade based on market demand. The world is also populated by non-player characters (NPCs) of varying friendliness. 

NMMO as a platform supports basic foraging tasks involving a few agents for a couple of minutes, thousand-agent joint survival + exploration + combat over multiple hours, and everything between. MMO settings allow player teams to interact in interesting ways and use entirely different strategies. 

**Our goal is to support a broad base of multiagent research that would be impractical or impossible to conduct using other environments.** Unlike other game genres typically used in research, MMOs simulate persistent worlds that support rich player interactions and a wider variety of progression strategies. These properties seem important to intelligence in the real world. An objective of this competition and platform is to spur research towards increasingly general and cognitively realistic environments. 

.. code-block:: python

   from nmmo import Env

   env = Env(config=None) # Default environment. Keep reading for config options
   obs = env.reset()

   while True:
      actions = {} # Compute with your model
      obs, rewards, dones, infos = env.step(actions)

Environments provide a standard PettingZoo API. Join our community Discord or WeChat and post in #support for help (do not raise Github issues for support). See the quick links for source code, baselines, latest publications, social media, and news!

General features of NMMO
  - Gameplay is on a map
  - Map has Water, Stone, and Grass tiles in a 128 x 128 array
  - A team has 8 Agents
  - There are 7 other teams competing in each round, each with 8 Agents as well
  - Goal is to have longest surviving Agent/s in gameplay round
  - Agents survive if they have HP


|icon| Agent Teams 
##################

**What do Agents Do?**

Your team of 8 Agents:
  - The ultimate goal is to score more points by completing more challenge tasks across the 1024 games than all other teams in that round.**
  - Have 8 individual professions that help them collect resources 
  - Use resources to increase Food, Water, and HP levels.
  - Collect resources to make ammunition 
  - Use ammunition to increase weapon power. You do more damage if you have ammo; ammo has levels; higher level ammo does more damage than lower. See Game Wiki**
  - Wear armor to protect themselves in combat
  - Defend or attack enemy Agents in combat using one of three styles (Range, Melee, Magic)
  - Buy and sell tools, consumables, armors, ammunitions, and weapons
  - Level up in all categories to increase power
  - Specialize in Professions, also known as skills. Each Agent has 8 and can level them all up. However, it’s not possible in the game to maximize all due to time limits. As such, what to max is a question of strategy. Different Agents on the same team can specialize in different Professions. 
  - Kill both NPC and enemy agents to gain items and increase score
  - Die when they run out of HP


The longest-lasting Agent in your team is the most important factor in your ranking score. How many kills your Agents complete is the second. 

There are 128 Agents at play at the start of a game round, making 16 teams of 8. Everyone plays at least 1000 rounds of the game, with assorted opponent teams assigned based on a matchmaking algorithm which optimizes for opponent teams of similar skill level. 

Your team is made up of 8 agents. Your ranking as a player after a round of gameplay is based on these factors:
  - Your Agent that stays alive longest
  - How many enemy Agents your team kills

In case of ties, ranking scores look at how many of your Agents survived to the end, and how healthy they were then. 

Keeping Agents Alive
********************

Agents stay alive by:
  - Eating food
  - Drinking water
  - Protecting HP in combat

*Discuss how Food and Water resources as well as mining function mechanistically.*
Agents have food / water bars starting on 100
Walk on food tile - regain full food. Tile disappears. Will respawn later, at a random time and same place. 
If you adjacent to water tile - regain full water. Done.
Skills - prospecting, carving, alchemy - walk on resource tile. Get the resource. Will respawn later, same place. Will be a different quality/level of resource, depending on Agent levels/tools.

About HP
********

If not taking damage, not hungry/thirsty will slowly regain HP
Food/Water levels go down each time tick. 
Scales: Lose 5 Food and 5 Water per game tick. Start with 100.
Lose 10 HP per tick if out of food. Lose 10 HP per tick if out of water. Lose 20 HP per tick if out of both food and water.
If above half food and half water, regain 10 HP per tick


Combat - is parrying back and forth, one attack per tick. Taking turns. Damage is a randomized function of confluence of factors. Include: Fighting style; combat skill level; weapon level; armor levels. 


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


Competition Environment 
***********************


Tile Spaces
Each environment contains an automatically generated tile-based game map of 128 x 128 tiles. Tiles come in three types:
  - Water (resource for water; for movement is an obstacle.)
  - Stone (obstacle)
  - Grass (passable)

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
   - Destroy an Item
      - *Reasons to sell an item - 
         - Item has no gameplay utility at that juncture, including no market value
         - Item would take too long to sell, and opportunity cost of space being occupied in inventory is higher
         - Inventory capacity is 12 items, including armor, weapon, tools, and consumables.

**TBD - whether one can Buy/Sell; Give and Destroy simultaneously

**Tile Resources**
On these tiles are various important resources. Access resources and stay alive in the game - EAT, DRINK and COMBAT.

**TODO: Port table**

**Market: Buy and Sell Resources**

Gold is the currency for buying and selling goods in NMMO. Gold comes in full units, and cannot be sub-divided. Gold is acquired by selling items, and used for buying items.

Prices are set by **Explain market pricing here
Agents set their own prices and receive gold when someone is willing to accept their price. Within the same team, can gift to one another. 

**TODO**


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

|icon| Gallery
##############

Perspective and UI
******************

.. figure:: /resource/image/minimal.png

| 

Overlays
********

.. figure:: /resource/image/overlays.png

| 

Multiscale Terrain Generation
*****************************

.. figure:: /resource/image/large_map.png

|

Overhead Render
***************

.. figure:: /resource/image/rendered_map.png

| 
