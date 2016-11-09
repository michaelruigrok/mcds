# mcds
mcds is a bash script which runs a minecraft server in the current terminal, 
but also lets you to specify server properties as command arguments. This allows
for very speedy swapping between different worlds, gamemodes, and a heap of
other restrictions and settings found in server.properties.

It may also be useful in the automation of specific configuration presets,
although the same can be achieved by simply swapping out the server.properties
file. But who knows, you might want to use this script to generate it in the
first place, or just to alter minor things.

##Usage:
    mcds [OPTIONS]

##Options
- All options take an argument and cannot be combined
- Double-dashed options are non-POSIX compliant, and take a spaced argument
    just like the single letter options
- BOOLEAN options can take any format you like: on/off, 1/0, true/false, yes/no,
    or set/clear
- STRING options can be anything, and thus have no checking whatsoever, so
    make sure they're valid
- NUMBER options must be numbers, but may require other unchecked restrictions
- Enumerated options (currently GAMEMODE and DIFFICULTY) can either be a
    number, or its corresponding name (e.g. 'P/peaceful' or 0 are correct).
    These ensure numbers are within range.


###Script Options/Config
    --help
        Print a help message, currently this text

    --args
        Print a quick summary of all the possible option parameters

    -U, --update-path DIRECTORY
        Updates the path that the script looks in for the server and its
        properties. Must be the first option, any options before it will
        affect the current set directory.

###Server Operation
    -P, --port, --server-port NUMBER
        set the port number used by the server

    -M, --message, --motd STRING
        sets the client's server-list message for the server

    -r, --rcon, --enable-rcon BOOLEAN
        enable or disable remote control
        
    -w, --whitelist, --white-list BOOLEAN
        enable or disable the white-list of accepted players

    -o, --online, --online-mode BOOLEAN
        enable or disable online mode player authentication

###Gameplay Settings
    -g, --gamemode GAMEMODE
        set the gamemode to either survival, creative, adventure or spectator

    -d, --difficulty DIFFICULTY
        set the difficulty to either peaceful, easy, normal or hard

    -h, --hardcore-mode, --hardcore BOOLEAN
        enable or disable hardcore mode, which puts players into spectator
        mode if they die

    -p, --pvp BOOLEAN
        enable or disable player-vs-player, allowing inter-player damage

    -f, --flight, --allow-flight BOOLEAN
        enable or disable player flight via mods

###World settings
    -l, --world, --level STRING
        set the world the server uses. Will create a new world if that world
        doesn't exist

    -R, --resource-pack STRING
        set a resource-pack that players can choose to use.

    -s, --seed, --level-seed STRING
        set the seed used for level generation

    -n, --nether, --allow-nether BOOLEAN
        allow players to access the nether

    -v, --view-distance NUMBER
        set the number of chunks a player can see

    -H, --height, --max-build-height NUMBER
        set the number of blocks high a player can build

###Spawn Settings
    -m, --monsters, --spawn-monsters BOOLEAN
        enable or disable the spawning of monsters

    -a, --animals, --spawn-animals BOOLEAN
        enable or disable the spawning of animals

    -c, --npcs, --spawn-npcs BOOLEAN
        enable or disable the spawning of non-player characters
