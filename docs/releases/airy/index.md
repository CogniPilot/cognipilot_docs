# About Airy Alicanto

An [Alicanto](https://en.wikipedia.org/wiki/Alicanto) is a bird from  Chilean mythology known to eat gold or silver and then glow. The bird is incapable of flight after overindulging on ore.

**Airy** Alicanto represents the origin of our light weight, and minimalistic software stack following a correct by construction software paradigm.

## Correct by Construction Design Drivers

We are not aiming to re-invent an opensource autopilot that can "fly anything" (there are many great autopilots for that ([PX4](https://px4.io/),  [ArduPilot](https://ardupilot.org/)), but instead focusing on state-of-the-art methologies for creating an autopilot with mathematically provable robustness properties. We are aiming to create a new generation of open source autopilot that can conduct safety critical missions such as transporting people, with a level of safety assurance not currently available in open source autopilot systems.

  * **Minimum Viable Code for the Mission**: By minimizing the lines of source code and branching, we ensure higher reliability, maintainability, and verifiability of the project. 

  * **Minimize Branch Statements in Control and Estimation Code**: We generally classify our code components into two areas. The first is low-level driver and application code. The second is guidance, control, and estimation code for the vehicle. We carefully consider the addition of each branch (if statement etc.) in our code for the estimator and controller as we are modelling the entire system mathematically, and each branch statement considerably complicates the verification task.

  * **Minimize Maintenance to Maintain Reliability**: Our goal is for CogniPilot to support a wide variety of vehicles (Planes, Copters, Boats, Rovers, Submersibles) and user applications while maintaining software integrity and reliaiblity. We plan to limit official support for each release to a minimal amount of vehicles for each class, while providing out of tree support via templates.

  * **Deprecate if No-longer Maintained**: On each release cycle, we will make a decision on whether to maintain official support for each vehicle platform or whether to adopt a new platform. This is to combat the slow creep in lines of code due to vehicle specific edge cases. 

# Currently supported platforms:

## Rover
   * MrBuggy3
   * ELM4

In our upcoming release, to be named, but going by B-Mythical (a mythical creature with a name starting with B), we plan to additionally support:

## Mulirotor
   * NXP RDDrone
   * TBD
## Submersible
   * TBD
## Plane
   * TBD

# Software Stack
* Ubuntu 22.04
* Zephyr RTOS 3.5
* ROS Humble
* Gazebo Harmonic

To get started see [Install](./getting_started/install.md)
