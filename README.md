# Mancala AI <br />
an old school project

### Jars
* KalahGame - Primary user inferface, allows a player to join or host a game and configure rules/settings
* HeadlessServer - Accepts incoming client connections and plays against them using an AI
* HeadlessServerMulti - Same as above, but able to play 100s of games simultaneously

<br />

## General Settings
Used by both the host and the client
* ai-name: MinMaxAI2
* use-GUI: true
* button-image: Circle
* port: 42374

## Game Settings
Used by the host to determine game rules
* holes-per-side: 6
* seeds-per-hole: 4
* time-limit: 5000 #Time limit in milliseconds
* starting-player: S #F=Me First, S=Me Second
* game-type: S #S=Standard,R=Random,C=Custom
* custom-board: 8 6 4 2 0 1 1 0 #Only used when `game-type: C`
* use-BEGIN: true

## Miscellaneous Settings
* empty-capture: false
* count-leftover-seeds: true
* last-host: localhost
* max-threads: 100

## KalahPlayer bots
There are many AIs (including some min-max AIs) to play against.<br>
A dropdown in the game menu lets users select an opponent type from the following list:
* HumanGUI  # Reads input from GUI
* HumanConsole  # Reads input from console
* RandomAI  # Chooses random valid moves
* DumbAI  # Chooses moves that land in its Kalah
* StrategicAI  # Chooses moves to maximize seeds won on each turn
* MinMaxAI  # Full AI with basic pruning and a clever utility function
* MinMaxAI2  # Adapted from above; adds multi-threading and basic pruning
* MinMaxAI3  # Adapted from above; uses a tree instead of a recursive function
* MinMaxAIFinal  # All features combined for a magnum opus / final submission
<br /><br />
MinMaxAIFinal has been the most thoroughly tested, and is what I recommended playing against

## Additional Features
AI
* Multiple difficulties
* Alpha-Beta Pruning
* Iterative Deepening
* Advanced Utility Function
* Mutli-threading
* Branch ordering (explores favorable branches sooner)
* Hax

GUI
* Custom board setup and seed placement
* Ability to edit the game
* Custom graphics for each individual game window
* Dynamicly updated timer on board
* Settings window to edit settings directly from within the game
* Automatically loads and saves settings to a easily configurable file (yml)
* Can by played using either GUI or a terminal

Networking
* The client and the server can both be run from the same menu
* Server can connect to multiple clients
* Game keeps track of last server successfully connected to
