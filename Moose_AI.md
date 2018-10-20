# AI Guide

![MOOSE AI](Images\MOOSE_AI.JPG)

This set of MOOSE classes take control of your AI.


## 1. [**AI A2A Dispatching**](Documentation/AI.AI_A2A_Dispatcher.html)

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
  * Quickly setup an A2A defense system using AI_A2A_GCICAP.
  * Setup a more advanced defense system using AI_A2A_DISPATCHER.


## 2. AI Cargo Dispatching

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


## 3. [**AI Balancing**](Documentation/AI.AI_Balancer.html)

![AI_Balancer](Images\AI_Balancing.JPG)

Balance player slots with AI to create an engaging simulation environment, independent of the amount of players.

**Features:**

  * Automatically spawn AI as a replacement of free player slots for a coalition.
  * Make the AI to perform tasks.
  * Define a maximum amount of AI to be active at the same time.
  * Configure the behaviour of AI when a human joins a slot for which an AI is active.


## 4. [**AI Large Formations**](Documentation/AI.AI_Formation.html)

![AI_Formation](Images\AI_Large_Formations.JPG)

Build large airborne formations of aircraft.

**Features:**

  * Build in-air formations consisting of more than 40 aircraft as one group.
  * Build different formation types.
  * Assign a group leader that will guide the large formation path.

## 5. AI engagement

### 5.1. [**AI Patrolling**](Documentation/AI.AI_Patrol.html)

![AI_Patrol](Images\AI_Air_Patrolling.JPG)

Peform Air Patrolling for airplanes within a patrol zone.

**Features:**

  * Patrol AI airplanes within a given zone.
  * Trigger detected events when enemy airplanes are detected.
  * Manage a fuel treshold to RTB on time.


### 5.2. [**AI Combat Air Patrolling**](Documentation/AI.AI_Cap.html)

![AI_Patrol](Images\AI_Combat_Air_Patrol.JPG)

Peform Combat Air Patrolling (CAP) for airplanes within a patrol zone.

**Features:**

  * Patrol AI airplanes within a given zone.
  * Trigger detected events when enemy airplanes are detected.
  * Manage a fuel treshold to RTB on time.
  * Engage the enemy when detected.

### 5.3. [**AI Close Air Support**](Documentation/AI.AI_Cas.html)

![AI_Patrol](Images\AI_Close_Air_Support.JPG)

Peform Close Air Support (CAS) near friendlies within an engagement zone.

**Features:**
 
  * Hold and standby within a patrol zone.
  * Engage upon command the enemies within an engagement zone.
  * Loop the zone until all enemies are eliminated.
  * Trigger different events upon the results achieved.
  * After combat, return to the patrol zone and hold.
  * RTB when commanded or after out of fuel.

### 5.4. [**AI Battlefield Air Interdiction**](Documentation/AI.AI_Bai.html)

![AI_Patrol](Images\AI_Battlefield_Air_Interdiction.JPG)

Peform Battlefield Air Interdiction (BAI) within an engagement zone.

**Features:**
 
  * Hold and standby within a patrol zone.
  * Engage upon command the assigned targets within an engagement zone.
  * Loop the zone until all targets are eliminated.
  * Trigger different events upon the results achieved.
  * After combat, return to the patrol zone and hold.
  * RTB when commanded or after out of fuel.

