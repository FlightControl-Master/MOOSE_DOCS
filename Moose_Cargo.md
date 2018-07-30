# MOOSE CARGO Guide

MOOSE implements a whole enhanced and new mechanism to create virtual cargo within your missions.
Cargo can be represented by groups, static objects, static cargo objects and can be boarded, loaded or sling loaded as part of
human or AI task dispatching!
In order to use the new MOOSE cargo management, system, you'll need to declare cargo objects as part of your mission script,
and setup either an AI or a human dispatcher to transport cargo around the battlefield.

Click on each individual class for detailed features and explanations!


## 1. AI Cargo Dispatching

You can make various AI transport cargo, setting up an automatic system that will make AI transport cargo (automatically)
through the battlefield. Depending on the type of AI, various classes are implemented:


### 1.1. [**AI\_CARGO\_DISPATCHER_APC**](Documentation/AI.AI_Cargo_Dispatcher_APC.html)

![AI_Cargo_Dispatcher_APC](Images\AI_Cargo_Dispatching_For_APC.JPG)

Models the intelligent transportation of infantry and other cargo using **APCs or trucks**.

**Features:**

  * The vehicles follow the roads to ensure the fastest possible cargo transportation over the ground.
  * Multiple vehicles can transport multiple cargo as one vehicle group.
  * Infantry loaded as cargo, will unboard in case enemies are nearby and will help defending the vehicles.
  * Different ranges can be setup for enemy defenses.


### 1.2. [**AI\_CARGO\_DISPATCHER_HELICOPTER**](Documentation/AI.AI_Cargo_Dispatcher_Helicopter.html)

![AI_Cargo_Dispatcher_Helicopter](Images\AI_Cargo_Dispatching_For_Helicopters.JPG)

Models the intelligent transportation of infantry and other cargo using **Helicopters**.

**Features:**

  * The helicopters will fly towards the pickup locations to pickup the cargo.
  * The helicopters will fly towards the deploy zones to deploy the cargo.
  * Precision deployment as well as randomized deployment within the deploy zones are possible.
  * Helicopters will orbit the deploy zones when there is no space for landing until the deploy zone is free.


## 1.3. [**AI\_CARGO\_DISPATCHER_AIRPLANE**](Documentation/AI.AI_Cargo_Dispatcher_Airplane.html)

![AI_Cargo_Dispatcher_Airplane](Images\AI_Cargo_Dispatching_For_Airplanes.JPG)

Models the intelligent transportation of infantry and other cargo using **Airplanes**.

**Features:**

  * The airplanes will fly towards the pickup airbases to pickup the cargo.
  * The airplanes will fly towards the deploy airbases to deploy the cargo.


## 2. Human cargo transportation dispatching.
 
Also **humans can achieve tasks** by to **transporting cargo** as part of a task or mission **goal**.

### 2.1. [**TASK\_CARGO\_DISPATCHER**](Documentation/Tasking.Task_Cargo_Dispatcher.html)

![TASK\_CARGO\_DISPATCHER](Images\Task_Cargo_Dispatcher.JPG)

The [**TASK\_CARGO\_DISPATCHER**](Documentation/Tasking.Task_Cargo_Dispatcher.html) allows you to setup various tasks for let human
players transport cargo as part of a task. 

The cargo dispatcher will implement for you mechanisms to create cargo transportation tasks:

  * As setup by the mission designer.
  * Dynamically create CSAR missions (when a pilot is downed as part of a downed plane).
  * Dynamically spawn new cargo and create cargo taskings!


## 3. Cargo management classes.

MOOSE has implemented **a separate system for cargo handling**.
It combines the capabilities of DCS world to combine infantry groups, cargo static objects and static objects
as "cargo" objects. Cargo classes provides a new and enhanced way to handle cargo management and transportation.
In order to use these MOOSE cargo facilities, you'll have to declare those groups and static objects
in a special way within your scripts and/or within the mission editor.

The main [**CARGO**](Documentation/Cargo.Cargo.html) class is the base class for all the cargo management.
It contains the required functionality to load / board / unload / unboard cargo, and manage the state of each cargo object.
From this CARGo class are other CARGO_ classes derived, which inherit the properties and functions from CARGO,
but implement a specific process to handle specific cargo objects!
It is not the purpose to use directly the CARGO class within your missions.
However, consult the CARGO documention as it provides a comprehensive description on how to manage cargo within your missions.


### 3.1. [**CARGO\_GROUP**](Documentation/Cargo.CargoGroup.html)

![CARGO\_GROUP](Images\Cargo_Groups.JPG)

Management of **moveable** and **grouped** cargo logistics, which are based on a [**GROUP**](Documentation/Wrapper.Group.html) object.
Typical cargo of this type can be infantry or (small) vehicles.

**Features:**

  * Board cargo into a carrier.
  * Unboard cargo from a carrier.
  * Automatic detection of destroyed cargo.
  * Respawn cargo.
  * Maintain cargo status.
  * Communication of cargo through messages.
  * Automatic declaration of group objects to be treated as MOOSE cargo in the mission editor!


### 3.2. [**CARGO_CRATE**](Documentation/Cargo.CargoCrate.html)

![CARGO\_CRATE](Images\Cargo_Crates.JPG)

Management of single cargo crates, which are based on a [**STATIC**](Documentation/Wrapper.Static.html) object.
Typical cargo of this type can be crates, oil barrels, wooden crates etc.
The cargo can be ANY static type! So potentially also other types of static objects can be treated as cargo!
Like flags, tires etc.

**Features:**

  * Loading / Unloading of cargo.
  * Automatic detection of destroyed cargo.
  * Respawn cargo.
  * Maintain cargo status.
  * Communication of cargo through messages.
  * Automatic declaration of group objects to be treated as MOOSE cargo in the mission editor!


### 3.3. [**CARGO_SLINGLOAD**](Documentation/Cargo.CargoSlingload.html)

![CARGO\_SLINGLOAD](Images\Cargo_Slingload.JPG)

Management of **sling loadable** cargo crates, which are based on a [**STATIC**](Documentation/Wrapper.Static.html) object. 
This cargo can only be slingloaded.

**Features:**

  * Slingload cargo.
  * Automatic detection of destroyed cargo.
  * Respawn cargo.
  * Maintain cargo status.
  * Communication of cargo through messages.
  * Automatic declaration of group objects to be treated as MOOSE cargo in the mission editor!


### 3.4. [**CARGO_UNIT**](Documentation/Cargo.CargoUnit.html)

![CARGO\_SLINGLOAD](Images\Cargo_Unit.JPG.JPG)

Management of **moveable** units, which are based on a [**UNIT**](Documentation/Wrapper.Unit.html) object. 
Note that this is an **Internal** class and is only mentioned here for reference!

