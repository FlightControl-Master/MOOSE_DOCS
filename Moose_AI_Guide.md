# AI. Usage Guide

## AI.1. A2A Dispatching

### AI.1.1. [**AI A2A Dispatcher**](Documentation/AI.AI_A2A_Dispatcher.html)

![AI A2A Dispatcher](Images\AI_Air_To_Air_Dispatching.JPG)

Create an **A2A defense system** executed by AI to perform CAP or GCI to defend your airspace.  
There are two classes that are important to learn:

   * [**AI\_A2A\_GCICAP**](Documentation/AI.AI_A2A_Dispatcher.html#AI_A2A_GCICAP)
   * [**AI\_A2A\_DISPATCHER**](Documentation/AI.AI_A2A_Dispatcher.html#AI_A2A_DISPATCHER)
   
The [**AI\_A2A\_GCICAP**](Documentation/AI.AI_A2A_Dispatcher.html#AI_A2A_GCICAP) is a class for **novice mission designers**, 
so I recommend novice users to start with using this class. 
You can quickly configure a working GCICAP process.
But it will provide less flexibility and options. 
If you want more options, use the [**AI\_A2A\_DISPATCHER**](Documentation/AI.AI_A2A_Dispatcher.html#AI_A2A_DISPATCHER).

**Features:**
 
  * Setup quickly an A2A defense system for a coalition.
  * Setup (CAP) Control Air Patrols at defined zones to enhance your A2A defenses.
  * Setup (GCI) Ground Control Intercept at defined airbases to enhance your A2A defenses.
  * Define and use an EWR (Early Warning Radar) network.
  * Define squadrons at airbases.
  * Enable airbases for A2A defenses.
  * Add different plane types to different squadrons.
  * Add multiple squadrons to different airbases.
  * Define different ranges to engage upon intruders.
  * Establish an automatic in air refuel process for CAP using refuel tankers.
  * Setup default settings for all squadrons and A2A defenses.
  * Setup specific settings for specific squadrons.
  * Quickly setup an A2A defense system using @{#AI_A2A_GCICAP}.
  * Setup a more advanced defense system using @{#AI_A2A_DISPATCHER}.

## AI.2. AI Cargo Dispatching

Cargo dispatching will make the AI to transport cargo to deploy zones.
Cargo can be transported by APC or trucks, or by helicopters.

**Overall Features:**

  * Quickly transport cargo to various deploy zones using different carrier types.
  * Various cargo types can be transported. These are infantry groups and crates.
  * Define a list of deploy zones of various types to transport the cargo to.
  * Multiple carrier groups can be enabled as one collaborating transportation process.
  * Different options can be setup to tweak the cargo transporation behaviour.
  * Home location that will be used for carrier parking, when all cargo has been transported.
  * Automatic activation of carriers when new cargo is to be picked-up (of cargo is spawned for example).

### AI.2.1. [**AI_Cargo_Dispatcher_APC**](Documentation/AI.AI_Cargo_Dispatcher_APC.html)

![AI_Cargo_Dispatcher_APC](Images\AI_Cargo_Dispatching_For_APC.JPG)

Models the intelligent transportation of infantry and other cargo using **APCs or trucks**.

**Specific Features:**

  * The vehicles follow the roads to ensure the fastest possible cargo transportation over the ground.
  * Multiple vehicles can transport multiple cargo as one vehicle group.
  * Infantry loaded as cargo, will unboard in case enemies are nearby and will help defending the vehicles.
  * Different ranges can be setup for enemy defenses.

### AI.2.2. [**AI_Cargo_Dispatcher_Helicopter**](Documentation/AI.AI_Cargo_Dispatcher_Helicopter.html)

![AI_Cargo_Dispatcher_Helicopter](Images\AI_Cargo_Dispatching_For_Helicopters.JPG)

Models the intelligent transportation of infantry and other cargo using **Helicopters**.

**Specific Features:**

  * The helicopters will fly towards the pickup locations to pickup the cargo.
  * The helicopters will fly towards the deploy zones to deploy the cargo.
  * Precision deployment as well as randomized deployment within the deploy zones are possible.
  * Helicopters will orbit the deploy zones when there is no space for landing until the deploy zone is free.


## AI.3. [**AI_Balancer**](Documentation/AI.AI_Balancer.html)

![AI_Balancer](Images\AI_Balancing.JPG)

Balance player slots with AI to create an engaging simulation environment, independent of the amount of players.

**Features:**

  * Automatically spawn AI as a replacement of free player slots for a coalition.
  * Make the AI to perform tasks.
  * Define a maximum amount of AI to be active at the same time.
  * Configure the behaviour of AI when a human joins a slot for which an AI is active.


## AI.4. [**AI_Formation**](Documentation/AI.AI_Formation.html)

![AI_Formation](Images\AI_Large_Formations.JPG)

Build large airborne formations of aircraft.

**Features:**

  * Build in-air formations consisting of more than 40 aircraft as one group.
  * Build different formation types.
  * Assign a group leader that will guide the large formation path.


