# MOOSE Usage Guide for Mission Designers.

## 1. MOOSE is an Object Oriented system.

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



## 2. MOOSE Framework Classes

MOOSE contains a lot of classes that can be used to enhance your missions.
Click on one of the links below to open the guides for each of the major areas that are covered by MOOSE.


### 2.1. [MOOSE AI Guide](Moose_AI.html)

MOOSE AI classes take control over the AI and makes the AI perform various activities. 


### 2.2. [MOOSE Tasking Guide](Moose_Tasking.html)

MOOSE Tasking Classes provide a comprehensive Mission Orchestration System.
Through COMMANDCENTERs, multiple logical MISSIONs can be orchestrated for coalitions.
Within each MISSION, various TASKs can be defined.
Each TASK has a TASK ACTION flow, which is the flow that a player (hosted by a UNIT) within the simulator needs to follow and accomplish.


## 2.3. [MOOSE Functional Guide](Moose_Functional.html)

MOOSE Functional Classes provide various functions that are useful in mission design.


## 2.4. [MOOSE Wrappers Guide](Moose_Wrappers.html)

MOOSE Wrapper Classes provide an object oriented hierarchical mechanism to manage the DCS objects within the simulator.
Wrapper classes provide another easier mechanism to control Groups, Units, Statics, Airbases and other objects.


## 2.5. [MOOSE Cargo Guide](Moose_Cargo.html)

MOOSE cargo classes provide the logical means to handle cargo transportation.


## 2.6. [MOOSE Core Guide](Moose_Core.html)

MOOSE core classes define the base building blocks of the MOOSE framework. 
These classes are also heavily used within the MOOSE framework.




## 3. MOOSE Demonstration Missions

The framework comes with demonstration missions which can be downloaded [here](https://github.com/FlightControl-Master/MOOSE_MISSIONS/releases), that you can try out and helps you to code.  
These missions provide examples of defined use cases how the MOOSE framework can be utilized. Each test mission is located in a separate directory, which contains at least one .lua file and .miz file.
The .lua file contains the mission script file that shows how the use case was implemented.
You can copy/paste code the code snippets from this .lua file into your missions, as it will accellerate your mission developments.
You will learn, see, and understand how the different MOOSE classes need to be applied, and how you can create
more complex mission scenarios by combining these MOOSE classes into a complex but powerful mission engine.

Some of these exact test missions are also demonstrated in a video format on the [YouTube channel](https://www.youtube.com/channel/UCjrA9j5LQoWsG4SpS8i79Qg).

![MOOSE framework](Presentations\MOOSE\Dia2.JPG)







