# MOOSE Usage Guide for Mission Designers.

## MOOSE is an Object Oriented system.

MOOSE is an Object Oriented framework and defines **Classes**, which are components that combine **Methods** and **Variables**/**Properties** as one encapsulated structure (table).
Mission Designers can what we call **Instantiate Objects** from these MOOSE classes.

An example of what this means is shortly explained using the SPAWN class of MOOSE, which you can use to spawn new groups into your running mission.
The SPAWN class simplifies the process of spawning, and it has many methods that you can use to create variations how you want your spawn object to spawn new groups.

```lua
local SpawnObject = SPAWN:New( "GroupName" ) -- This creates a new SpawnObject from the SPAWN class, using the :New method constructor to instantiate a new SPAWN object searching for the GroupName as the late activated group defined within your Mission Editor.  
-- Nothing is spawned yet..., so let's use now the SpawnObject to spawn a new GROUP.

local SpawnGroup = SpawnObject:Spawn() -- Here we use the :Spawn() method of the SPAWN class. This method creates a new group from the GroupName template as defined within the Mission Editor.
```

MOOSE Classes **derive or inherit** from each other, that means, within MOOSE there is an **Inheritance** structure where **inherited MOOSE Classes** are re-using properties and methods from the **Parent MOOSE Class**.
This powerful concept is used everywhere within the MOOSE framework. The main (Parent) Class in the MOOSE framework is the BASE class. Every MOOSE Class is derived from this top BASE Class.
So is also the SPAWN class derived from the BASE class. The BASE class provides powerful methods for debugging, event handling and implements the class handling logic.
As a normal MOOSE user, you won't implement any code using inheritance but just know that the inheritance structure is omni present in the intellisense and documentation.
You'll need to browse to the right MOOSE Class within the inheritance tree structure to identify which methods are properties are defined for which class.

## MOOSE Framework is a set of **Classes** to be used by Mission Designers.

MOOSE contains a lot of classes that can be used to enhance your missions.
There are AI classes, which provide you with the tools to control AI.
Tasking classes will let human players perform tasks with mission goals.

In a nuttshell, this is what MOOSE can do for you.

### AI Classes

The AI classes are designed to make AI perform processes. 
I use the term processes here, because the AI classes will make the controllable AI to perform a series of tasks that will result in a goal to be achieved.

In summary, there are different types of AI classes within the MOOSE framework, that will make AI perform various types of processes.

#### AI A2A Dispatching

##### [**AI A2A Dispatcher**](Documentation/AI.AI_A2A_Dispatcher.html)

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

#### AI Cargo Dispatching

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

##### [**AI_Cargo_Dispatcher_APC**](Documentation/AI.AI_Cargo_Dispatcher_APC.html)

![AI_Cargo_Dispatcher_APC](Images\AI_Cargo_Dispatching_For_APC.JPG)

Models the intelligent transportation of infantry and other cargo using **APCs or trucks**.

**Specific Features:**

  * The vehicles follow the roads to ensure the fastest possible cargo transportation over the ground.
  * Multiple vehicles can transport multiple cargo as one vehicle group.
  * Infantry loaded as cargo, will unboard in case enemies are nearby and will help defending the vehicles.
  * Different ranges can be setup for enemy defenses.

##### [**AI_Cargo_Dispatcher_Helicopter**](Documentation/AI.AI_Cargo_Dispatcher_Helicopter.html)

![AI_Cargo_Dispatcher_Helicopter](Images\AI_Cargo_Dispatching_For_Helicopters.JPG)

Models the intelligent transportation of infantry and other cargo using **Helicopters**.

**Specific Features:**

  * The helicopters will fly towards the pickup locations to pickup the cargo.
  * The helicopters will fly towards the deploy zones to deploy the cargo.
  * Precision deployment as well as randomized deployment within the deploy zones are possible.
  * Helicopters will orbit the deploy zones when there is no space for landing until the deploy zone is free.


#### [**AI_Balancer**](Documentation/AI.AI_Balancer.html)

![AI_Balancer](Images\AI_Balancing.JPG)

Balance player slots with AI to create an engaging simulation environment, independent of the amount of players.

** Features:**

  * Automatically spawn AI as a replacement of free player slots for a coalition.
  * Make the AI to perform tasks.
  * Define a maximum amount of AI to be active at the same time.
  * Configure the behaviour of AI when a human joins a slot for which an AI is active.


#### [**AI_Formation**](Documentation/AI.AI_Formation.html)

![AI_Formation](Images\AI_Large_Formations.JPG)

Build large airborne formations of aircraft.

**Features:**

  * Build in-air formations consisting of more than 40 aircraft as one group.
  * Build different formation types.
  * Assign a group leader that will guide the large formation path.


## MOOSE Demonstration Missions

The framework comes with demonstration missions which can be downloaded [here](https://github.com/FlightControl-Master/MOOSE_MISSIONS/releases), that you can try out and helps you to code.  
These missions provide examples of defined use cases how the MOOSE framework can be utilized. Each test mission is located in a separate directory, which contains at least one .lua file and .miz file.
The .lua file contains the mission script file that shows how the use case was implemented.
You can copy/paste code the code snippets from this .lua file into your missions, as it will accellerate your mission developments.
You will learn, see, and understand how the different MOOSE classes need to be applied, and how you can create
more complex mission scenarios by combining these MOOSE classes into a complex but powerful mission engine.

Some of these exact test missions are also demonstrated in a video format on the [YouTube channel](https://www.youtube.com/channel/UCjrA9j5LQoWsG4SpS8i79Qg).

![MOOSE framework](Presentations\MOOSE\Dia2.JPG)

## 2.2. MOOSE Human Tasking Classes

MOOSE Tasking Classes provide a comprehensive Mission Orchestration System.
Through COMMANDCENTERs, multiple logical MISSIONs can be orchestrated for coalitions.
Within each MISSION, various TASKs can be defined.
Each TASK has a TASK ACTION flow, which is the flow that a player (hosted by a UNIT) within the simulator needs to follow and accomplish.

* [**COMMANDCENTER**](Documentation/Tasking.CommandCenter.html): Orchestrates various logical MISSIONs for a coalition.

* [**MISSION**](Documentation/Tasking.Mission.html): Each MISSION has various TASKs to be executed and accomplished by players.

* [**TASK_A2A_DISPATCHER**](Documentation/Tasking.Task_A2A_Dispatcher.html): Automatically and dynamically dispatch A2A tasks to be executed by human players, as a result of the detection of airborne targets within a Mission scope.

* [**TASK_A2G_DISPATCHER**](Documentation/Tasking.Task_A2G_Dispatcher.html): Automatically and dynamically dispatch A2G tasks to be executed by human players, as a result of the detection of ground targets within a Mission scope.

* [**TASK_A2A**](Documentation/Tasking.Task_A2A.html): Models a A2A CAP, INTERCEPT and SWEEP tasks where a Player is routed towards an attack zone without enemies nearby, and various ground targets need to be eliminated.

* [**TASK_A2G**](Documentation/Tasking.Task_A2G.html): Models a A2G SEAD, CAS and BAI tasks where a Player is routed towards an attack zone with enemies nearby, and various ground targets need to be eliminated.


## 2.2. MOOSE AI Controlling Classes

MOOSE AI Controlling Classes provide mechanisms to control AI over long lasting processes.  
These AI Controlling Classes are based on FSM (Finite State Machine) Classes, and provided an encapsulated way to make AI behave or execute an activity.

* [**AI A2A Defenses**](Documentation/AI.AI_A2A_Dispatcher.html): Create automatic A2A defense systems executed by AI and perform CAP or GCI.
   * [**AI\_A2A\_GCICAP**](Documentation/AI.AI_A2A_Dispatcher.html#AI_A2A_GCICAP): Using an easy process you can define an A2A defense system using the Mission Editor.
   * [**AI\_A2A\_DISPATCHER**](Documentation/AI.AI_A2A_Dispatcher.html#AI_A2A_DISPATCHER): Same as AI\_A2A\_GCICAP, but is for more advanced or developer type mission designers. This class provides more options.

* [**AI\_BALANCER**](Documentation/AI.AI_Balancer.html): Compensate in a multi player mission the abscence of players with dynamically spawned AI air units. When players join CLIENTS, the AI will either be destroyed, or will fly back to the home or nearest friendly airbase.

* [**AI\_BAI**](Documentation/AI.AI_Bai.html): Make an alive AI Group perform Battlefield Air Interdiction as a dynamic process.

* [**AI\_CAP**](Documentation/AI.AI_Cap.html): Make an alive AI Group perform Combat Air Patrol as a dynamic process.

* [**AI\_CAS**](Documentation/AI.AI_Cas.html): Make an alive AI Group perform Close Air Support as a dynamic process.

* [**AI\_PATROL**](Documentation/AI.AI_Patrol.html): Make an alive AI Group perform an Air Patrol as a dynamic process.


## 2.3. MOOSE Functional Classes

MOOSE Functional Classes provide various functions that are useful in mission design.

* [**ATC_GROUND**](Documentation/Functional.ATC_Ground.html): Monitor players on the airbase and make them behave and provide instructions.
  * [**ATC_GROUND**](Documentation/Functional.ATC_Ground.html#ATC_GROUND_CAUCASUS): ATC Ground operations for Caucasus.
  * [**ATC_GROUND**](Documentation/Functional.ATC_Ground.html#ATC_GROUND_NEVADA): ATC Ground operations for Nevada.
  * [**ATC_GROUND**](Documentation/Functional.ATC_Ground.html#ATC_GROUND_NORMANDY): ATC Ground operations for Normandy.

* [**CLEANUP\_AIRBASE**](Documentation/Functional.CleanUp.html): Keeps the airbases clean from clutter. (Only partly functional due to a bug in DCS, destroyed objects cannot be removed).

* [**DESIGNATE**](Documentation/Functional.Designate.html): Make AI automatically designate detected targets, and provide menu options for players to give instructions to the AI how to designate (by laser, smoke or illumination).

* [**DETECTION**](Documentation/Functional.Detection.html): Detect other units using the available sensors of the detection unit. The DETECTION_BASE derived classes will provide different methods how the sets of detected objects are built.

* [**ESCORT**](Documentation/Functional.Escort.html): Makes groups consisting of helicopters, airplanes, ground troops or ships within a mission joining your flight. You can control these groups through the ratio menu during your flight. Available commands are around: Navigation, Position Hold, Reporting (Target Detection), Attacking, Assisted Attacks, ROE, Evasion, Mission Execution and more ...

* [**MISSILETRAINER**](Documentation/Functional.MissileTrainer.html): Missile trainer, it destroys missiles when they are within a certain range of player airplanes, displays tracking and alert messages of missile launches; approach; destruction, and configure with radio menu commands. Various APIs available to configure the trainer.

* [**RAT**](Documentation/Functional.Rat.html): Random Air Traffic engine developed by FunkyFranky, use the available airspace!

* [**RANGE**](Documentation/Functional.Range.html): Enables easy set up of bombing and strafing ranges within DCS World.

* [**SCORING**](Documentation/Functional.Scoring.html): Administer the scoring of player achievements, and create a CSV file logging the scoring events for use at team or squadron websites.

* [**SEAD**](Documentation/Functional.Sead.html): Make SAM sites avoid SEAD missiles being fired at.

* [**ZONE\_CAPTURE\_COALITION**](Documentation/Functional.ZoneCaptureCoalition.html): Create a zone capturing process around a zone! Zones can be guarded, attacked, empty or captured.


## 2.4. MOOSE Wrapper Classes

MOOSE Wrapper Classes provide an object oriented hierarchical mechanism to manage the DCS objects within the simulator.
Wrapper classes provide another easier mechanism to control Groups, Units, Statics, Airbases and other objects.

* [**AIRBASE**](Documentation/Wrapper.Airbase.html): This class wraps a DCS Airbase object within the simulator.

* [**CLIENT**](Documentation/Wrapper.Client.html): This class wraps a DCS Unit object within the simulator, which has a skill Client or Player.  

* [**CONTROLLABLE**](Documentation/Wrapper.Controllable.html): This class provides the base for MOOSE controllable objects. These are GROUPs, UNITs, CLIENTs.

* [**GROUP**](Documentation/Wrapper.Group.html): This class wraps a DCS Group objects within the simulator.  

* [**IDENTIFIABLE**](Documentation/Wrapper.Identifiable.html): This class provides the base for MOOSE identifiable objects, which is every object within the simulator :-).

* [**POSITIONABLE**](Documentation/Wrapper.Positionable.html): This class provides the base for MOOSE positionable objects. These are AIRBASEs, STATICs, GROUPs, UNITs ...

* [**OBJECT**](Documentation/Wrapper.Object.html): This class provides the base for MOOSE objects.

* [**STATIC**](Documentation/Wrapper.Static.html): This class wraps a DCS StaticObject object within the simulator. 

* [**UNIT**](Documentation/Wrapper.Unit.html): This class wraps a DCS Unit object within the simulator.


## 2.5. MOOSE Core Classes

* [**CARGO**](Documentation/Cargo.Cargo.html): Manage Cargo in the simulation.  
* [**CARGO\_GROUP**](Documentation/Cargo.Cargo.html#CARGO_GROUP): Manage Cargo that is defined as a GROUP object within the simulation.  
* [**CARGO\_CRATE**](Documentation/Cargo.Cargo_Crate.html#CARGO_CRATE): Manage Cargo that is defined as a CARGO STATIC object within the simulation.  
* [**CARGO\_SLINGLOAD**](Documentation/Cargo.Cargo_Slingload.html#CARGO_SLINGLOAD): Manage Cargo that is defined as a CARGO STATIC object within the simulation to be sling loaded.  


## 2.6. MOOSE Core Classes

These classes define the base building blocks of the MOOSE framework. These classes are heavily used within the MOOSE framework.

* [**BASE**](Documentation/Core.Base.html): The main class from which all MOOSE classes are derived from. The BASE class contains essential functions to support inheritance and MOOSE object execution tracing (logging within the DCS.log file in the saved games folder of the user).

* [**BEACON**](Documentation/Core.Radio.html): Create beacons.  

* [**COORDINATE**](Documentation/Core.Point.html): Manage 2D and 3D points in the simulation space, and use its methods for various actions on the coordinate.  
* [**POINT\_VEC2**](Documentation/Core.Point.html#POINT_VEC2): Manage 2D points in the simulation space.  
* [**POINT\_VEC3**](Documentation/Core.Point.html#POINT_VEC3): Manage 3D points in the simulation space.  


* [**DATABASE**](Documentation/Core.Database.html): Creates a collection of GROUPS[], UNITS[], CLIENTS[] and managed these sets automatically. Provides an API set to retrieve a GROUP, UNIT or CLIENT instance from the _DATABASE object using defined APIs. The collections are maintained dynamically during the execution of the mission, so when players join, leave, when units are created or destroyed, the collections are dynamically updated.

* [**EVENT**](Documentation/Core.Event.html): Provides the Event Dispatcher base class to handle DCS Events, being fired upon registered events within the DCS simulator. Note that EVENT is used by BASE, exposing OnEvent() methods to catch these DCS events.

* [**FSM**](Documentation/Core.Fsm.html:  The main FSM class can be used to build a generic Finite State Machine. Finite State Machine provides a process management or state machine capability for various scenarios.    
* [**FSM\_CONTROLLABLE**](Documentation/AI.Fsm.html#FSM_CONTROLLABLE):  An FSM class to control a Controllable. A controllable is a group or unit that can be controlled.  

* [**MENU**](Documentation/Core.Menu.html): Set Menu options under the radio menu (F10). MENU classes also manage the recursive removal of menus, and the intelligent refresh of menu options (only the changes are applied).  
* [**MENU\_MISSION**](Documentation/Core.Menu.html#MENU_MISSION): Set a main menu structure for the complete mission, for all players.  
* [**MENU\_MISSION\_COMMAND**](Documentation/Core.Menu.html#MENU_MISSION_COMMAND): Set a main menu command for the complete mission, for all players.  
* [**MENU\_COALITION**](Documentation/Core.Menu.html#MENU_COALITION): Set a menu structure for a coalition, for all players of that coalition.  
* [**MENU\_COALITION\_COMMAND**](Documentation/Core.Menu.html#MENU_COALITION_COMMAND): Set a menu command for a coalition, for all players of that coalition.  
* [**MENU\_GROUP**](Documentation/Core.Menu.html#MENU_GROUP): Set a menu structure for a group, for all players of that group.  
* [**MENU\_GROUP\_COMMAND**](Documentation/Core.Menu.html#MENU_GROUP_COMMAND): Set a menu command for a group, for all players of that group.  

* [**MESSAGE**](Documentation/Core.Message.html): A message publishing system, displaying messages to Clients, Coalitions or All players. 

* [**SET**](Documentation/Core.Set.html): Create SETs of MOOSE objects. The SET can be filtered with defined filter criteria. Iterators are available that iterate through the SET, calling a function for each object within the SET. 
* [**SET\_AIRBASE**](Documentation/Core.Set.html#SET_AIRBASE): Create a SET of AIRBASE objects.  
* [**SET\_CARGO**](Documentation/Core.Set.html#SET_CARGO): Create a SET of CARGO objects.  
* [**SET\_CLIENT**](Documentation/Core.Set.html#SET_CLIENT): Create a SET of CLIENT objects.  
* [**SET\_GROUP**](Documentation/Core.Set.html#SET_GROUP): Create a SET of GROUP objects.  
* [**SET\_UNIT**](Documentation/Core.Set.html#SET_UNIT): Create a SET of UNIT objects.  
* [**SET\_ZONE**](Documentation/Core.Set.html#SET_ZONE): Create a SET of ZONE_BASE objects.  

* [**RADIO**](Documentation/Core.Radio.html): Create radio communication.  

* [**SCHEDULER**](Documentation/Core.Scheduler.html): This class implements a timer scheduler that will call at optional specified intervals repeatedly or just one time a scheduled function.

* [**SETTINGS**](Documentation/Core.Settings.html): The management of Default system settings or specific Player settings that configure the behaviour of MOOSE classes. 

* [**SPAWN**](Documentation/Core.Spawn.html#SPAWN): Spawn new groups (and units) during mission execution.

* [**SPAWNSTATIC**](Documentation/Core.SpawnStatic.html#SPAWNSTATIC): Spawn Static objects using a predefined "template".  

* [**ZONES**](Documentation/Core.Zone.html#ZONE): Create a zone object from a trigger zone as defined in the Mission Editor.  
* [**ZONE\_GROUP**](Documentation/Core.Zone.html#ZONE_GROUP): Create a zone object around a group on the battlefield, with a defined radius. The first object in the group has the zone, and is thus a moving zone!  
* [**ZONE\_POLYGON**](Documentation/Core.Zone.html#ZONE_POLYGON): Create a zone object from a group object, which is late activated, and its route points define the zone.  
* [**ZONE\_RADIUS**](Documentation/Core.Zone.html#ZONE_RADIUS): Create a zone object from a 2D vector on the battlefield, with a defined radius.  
* [**ZONE\_UNIT**](Documentation/Core.Zone.html#ZONE_UNIT): Create a zone object around a unit on the battlefield, with a defined radius. This, this zone is a moving zone!  

