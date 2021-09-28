# Matrix ideas
Matrix is "an open network for secure, decentralized communication".

The following ideas would be cool to implement, but for many I lack the time or motivation to build and maintain a project.

## Service: Public transport

Allows to chat with others who are on the same train / bus while also providing the ride's status (services, delays, etc.) via Matrix.

* https://zugchat.de/

### Implementation ideas 

* Basic rooms (MVP)
  * Every transit line becomes a room.
  * A website lists all rooms.
* Live information
  * Post delay information as a room state.

## Bridge: Issue boards (GitLab / GitHub)

Making Issue boards a bit more decentral by bridging them to Matrix.

### Why?

* Allows the project owners to own a copy of all issue / pull request discussions.
* Allows Matrix users without a GitHub account to participate
* Allows to receive Matrix notifications when new progress is being made on an issue / pull request.

### Implementation ideas

* Basic bridge (MVP)
  * Github issues / pull requests become rooms
  * Comments on issues and pull requests are bridged both ways as messages
  * Status changes on issues and pull requests are bridged as notices
* Space structure (making it useful)
  * Github users / organisations become a Space each
    * they contain the repositories as Sub-Spaces
  * GitHub repositories become a Space each
    * they contain the issues and pull requests as rooms
* Reviews (nice to have)
  * _requires Matrix users to connect their Github account_
  * A Matrix user can approve a pull request by posting "Approve: <message>"
    * An approval can be withdrawn by deleting the Matrix message.
  * A Matrix user can request changes to a pull request by posting "Request changes: <message>"
    * Also allow "Request change: <message>" and "Deny: "
    * A request of changes can be withdrawn by deleting the Matrix message.

## Game: Multi User Dungeon (MUD)

The player controls a character in a text-based video game. The game world consists of many rooms, each may contain Non-Player-Characters (NPCs) with quests, foes, loot or other mysteries.

* A player creates a character with various skills in fighting, defence and magic which can be leveled up by fighting.
* A player can change to a different room by posting a direction, like "West", "East" or "South".

### Why?

* Allows players to play in their chat app.
* Allows players to own a log of their playthrough.
* Has the potential for social interaction, given that players are connected to people they know on Matrix.

### Inspiration
* Dungeon and Dragons with its character sheets, skills and adventures purely conveyed through language
* Telnet-based MUDs like [Aardwolf](https://www.aardwolf.com/)

### Implementation ideas

* Store the character's information as room state.
  * The player owns the data by having a copy.
  * The game could be continued by a different appservice, if the first one goes down.
