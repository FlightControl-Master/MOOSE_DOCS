# MOOSE CARGO Guide

## [**CARGO**](Documentation/Cargo.Cargo.html)

Management of CARGO logistics, 
that can be transported from and to transportation carriers.

Note that CARGO is a **base** class, from which other cargo classes are derived!
It is not the purpose to use directly the CARGO class within your missions.

Instead, you can declare cargo within your missions of the following types:

## 1. [**CARGO\_GROUP**](Documentation/Cargo.CargoGroup.html)

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


## 2. [**CARGO_CRATE**](Documentation/Cargo.CargoCrate.html)

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


## 3. [**CARGO_SLINGLOAD**](Documentation/Cargo.CargoSlingload.html)

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


## 4. [**CARGO_UNIT**](Documentation/Cargo.CargoUnit.html)

![CARGO\_SLINGLOAD](Images\Cargo_Unit.JPG.JPG)

Management of **moveable** units, which are based on a [**UNIT**](Documentation/Wrapper.Unit.html) object. 
Note that this is an **Internal** class and is only mentioned here for reference!

