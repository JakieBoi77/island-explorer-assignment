# Island Explorer Assignment

### Authors
  - [Jake Finlay](finlaj11@mcmaster.ca) 
  - [Vikram Chandar](chandarv@mcmaster.ca)
  - [Arjun Sasidaran](sasidara@mcmaster.ca)

## Project Description

Me and my colleagues were hired by the Outer Wilds Department of ACME Corp (A Compnay that Makes Everyting) to work on their _Rescue Drone System_. The system aimed to support the resucing of individuals by finding a safe place for a rescue team to land on an unexplored island.

The Outer Wilds department specialized in outdoor rescue and have developed long-range drone technology to cover large areas and support rescuing in hostile environments.

The main problem with the Outer Wilds department is they did not followed an interative and incremental approach. They focussed on bulidng the hardware and postponed the implementation of the controller. As a result of this, the Outer Wilds departement created a $100 000 drone with no way to control it!

It was our job to solve this issue.

## Product Description

This product is an _exploration command center_ for the [Island](https://ace-design.github.io/island/) serious game. 

- The `ca.mcmaster.se2aa4.island.team_XXX_.Explorer` class implements the command center, used to compete with the others. (XXX being the team identifier)
- The `Runner` class allows one to run the command center on a specific map.


## How to compile, run and deploy

### Compiling the project:

```
mosser@azrael a2-template % mvn clean package
...
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.960 s
[INFO] Finished at: 2024-01-20T18:26:43-05:00
[INFO] ------------------------------------------------------------------------
mosser@azrael a2-template % 
```

This creates one jar file in the `target` directory, named after the team identifier (i.e., team 00 uses `team00-1.0.jar`).

As the project is intended to run in the competition arena, this jar is not executable. 

### Run the project

The project is not intended to be started by the user, but instead to be part of the competition arena. However, one might one to execute their command center on local files for testing purposes.

To do so, we ask maven to execute the `Runner` class, using a map provided as parameter:

```
mosser@azrael a2-template % mvn exec:java -q -Dexec.args="./maps/map03.json"
```

It creates three files in the `outputs` directory:

- `_pois.json`: the location of the points of interests
- `Explorer_Island.json`: a transcript of the dialogue between the player and the game engine
- `Explorer.svg`: the map explored by the player, with a fog of war for the tiles that were not visited.