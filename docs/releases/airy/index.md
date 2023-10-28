# About Airy Alicanto

An [Alicanto](https://en.wikipedia.org/wiki/Alicanto) is a bird from  Chilean mythology known to eat gold or silver and then glow. The bird is incapable of flight after overindulging on ore.

**Airy Alicanto** represents the origin of CogniPilot's light weight, and minimalistic software stack following a correct by construction software paradigm.

## Correct by Construction Design Drivers

CogniPilot is not aiming to re-invent an opensource autopilot that can be a drop in replacement for use in Hobby drones, FPV Racing drones, or a wide variety of DIY autonomous vehicles, there are many great autopilots for that ([ArduPilot](https://ardupilot.org/), [BetaFlight](https://betaflight.com/), [PX4](https://px4.io/)). CogniPilot instead focuses on state-of-the-art methologies for creating an autopilot with mathematically provable robustness properties. In order to achieve this level of reliability, accurate mathematical models of the vehicle and control software must be established that are beyond the expected domain of many hobbyists. However, for those willing to pursue the extra steps to create a mathematical model of their vehicle, templates are available to enable out of tree custom vehicles. CogniPilot is a new class of open source autopilot that can conduct safety critical missions such as transporting people, with a level of safety assurance not currently available in other open source autopilots.

  * **Minimum Viable Code for the Mission**: By minimizing the lines of source code and branching, CogniPilot ensures higher reliability, maintainability, and verifiability of the project. 

  * **Minimize Branch Statements in Control and Estimation Code**: CogniPilot generally classifies its code components into two areas. The first is low-level driver and application code. The second is guidance, control, and estimation code for the vehicle. Developers carefully consider the addition of each branch (if statement etc.) in the code for the estimator and controller, as developers are modelling the entire system mathematically. Each branch statement considerably complicates the verification task.

  * **Minimize Maintenance to Maintain Reliability**: A goal of CogniPilot is to support a wide variety of vehicles (Planes, Copters, Boats, Rovers, Submersibles) and user applications while maintaining software integrity and reliaiblity. CogniPilot plans to limit official support for each release to a minimal amount of vehicles for each class, while providing out of tree support via templates.

  * **Deprecate if No-longer Maintained**: On each release cycle, the CogniPilot technical steering committee (TSC) will make a decision on whether to maintain official support for each vehicle platform or whether to adopt a new platform. This is to combat the slow creep in lines of code due to vehicle specific edge cases. 

# Currently supported platforms:

## Rover
   * MrBuggy3
   * ELM4

CogniPilot's upcoming release, to be named, but going by B-Mythical (a mythical creature with a name starting with B) will have planned additional support for:

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
* ROS 2 Humble
* Gazebo Garden

To get started see [Install](./getting_started/install.md)
