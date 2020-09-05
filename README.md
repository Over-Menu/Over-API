# Over-API
## Table of contents
* [General info](#general-info)
* [First steps](#first-steps)
* [Functions](#Functions)

## General info
#### Foreword:
You wanted to write your own functions for Over? Then you are right here!
We recommend to read this documentation completely to understand the functions, if you have any questions, we are available on the discord.
#### Requirements:
* Visual Studio or Visual Studio Code
* Some LUA experience
* The Over-Menu
#### LUA Information:
You can use the vanilla LUA without any changes.
	
## First steps
* Hello World! [Not recommended]
```lua
io.write(string.format("Hello World!")) -- Basic LUA Hello world (Not recommended because the format of the Over console are not included!)
```
* Hello World! [Recommended]
```lua
LogConsoleMessage("Hello World!") -- Basic Over Console output (Recommended because the format of the Over console are used!)
```
* Basic Function call
```lua
SetWantedLevel(GetPlayerPedId() --[[ Local Player Index ]], 1 --[[ Wanted Level]] )
```


## Functions
Here a Functions list with examples:
* [Player](#Player)
* [Vehicle](#Vehicle)
* [Gameplay](#Gameplay)
* [Entity](#Entity)
* [Streaming](#Streaming)
* [Stats](#Stats)
* [API](#API)

## Player
### GetPlayerPedId:
#### Arguments:
```cpp
int GetPlayerPedId()
```
#### Example:
```lua
ThisFunctionNeedAPlayerIndex(GetPlayerPedId())
```
### GetPlayerId:
#### Arguments:
```cpp
int GetPlayerId()
```
#### Example:
```lua
ThisFunctionNeedAPlayerId(GetPlayerId())
```

### SetWantedLevel:
#### Arguments:
```cpp
void SetWantedLevel(int playerindex, int wantedlevel)
```
#### Example:
```lua
SetWantedLevel(GetPlayerPedId(), 3)
```

### SetPlayerName:
#### Arguments:
```cpp
void SetPlayerName(string name)
```
#### Example:
```lua
SetPlayerName("Example")
```

## Vehicle
### GetPlayerCurrentVehicle:
#### Arguments:
```cpp
int GetPlayerCurrentVehicle(int playerindex)
```
#### Example:
```lua
GetPlayerCurrentVehicle(GetPlayerPedId())
```

### SetVehicleHeadLightsColor:
#### Arguments:
```cpp
void SetVehicleHeadLightsColor(int vehicle, int colorid)
```
#### Example:
```lua
SetVehicleHeadLightsColor(GetPlayerCurrentVehicle(GetPlayerPedId()), 12)
```

### GetVehicleHeadLightsColor:
#### Arguments:
```cpp
int GetVehicleHeadLightsColor(int vehicle)
```
#### Example:
```lua
GetVehicleHeadLightsColor(GetPlayerCurrentVehicle(GetPlayerPedId()))
```

### SetVehicleNeonLightsColor:
#### Arguments:
```cpp
void SetVehicleNeonLightsColor(int vehicle, int r, int g, int b)
```
#### Example:
```lua
SetVehicleNeonLightsColor(GetPlayerCurrentVehicle(GetPlayerPedId()), 255, 75, 15)
```

### SetVehicleNeonLightEnabled:
#### Arguments:
```cpp
void SetVehicleNeonLightEnabled(int vehicle, int index, bool toggle)
```
#### Example:
```lua
SetVehicleNeonLightEnabled(GetPlayerCurrentVehicle(GetPlayerPedId()), 2, true)
```

### IsVehicleNeonLightEnabled:
#### Arguments:
```cpp
bool IsVehicleNeonLightEnabled(int vehicle, int index)
```
#### Example:
```lua
IsVehicleNeonLightEnabled(GetPlayerCurrentVehicle(GetPlayerPedId()), 2)
```

### SetVehiclePlateText:
#### Arguments:
```cpp
bool SetVehiclePlateText(int vehicle, string text)
```
#### Example:
```lua
SetVehiclePlateText(GetPlayerCurrentVehicle(GetPlayerPedId()), "Example")
```

### VehicleSpawner:
#### Arguments:
```cpp
void VehicleSpawner(string vehiclename)
```
#### Example:
```lua
VehicleSpawner("zentorno")
```

### CreateVehicle:
#### Arguments:
```cpp
int CreateVehicle(Hash modelHash, float x, float y, float z, float heading, bool isNetwork, bool thisScriptCheck)
```
#### Example:
```lua
CreateVehicle(GetHashKey("zentorno"), GetEntityCoords(GetPlayerPedId(), true, "x"), GetEntityCoords(GetPlayerPedId(), true, "y"), GetEntityCoords(GetPlayerPedId(), true, "z"), GetEntityHeading(GetPlayerPedId()), true, true)
```

## Entity
### DoesEntityExist:
#### Arguments:
```cpp
bool DoesEntityExist(int entity)
```
#### Example:
```lua
DoesEntityExist(GetPlayerPedId())
```

### GetEntityCoords:
#### Arguments:
```cpp
int GetEntityCoords(int entity, bool alive, string xyz)
```
#### Example:
```lua
GetEntityCoords(GetPlayerPedId(), true, "x")
```

### SetEntityCoords:
#### Arguments:
```cpp
void SetEntityCoords(int entity, float xPos, float yPos, float zPos, DWORD xAxis, DWORD yAxis, DWORD zAxis, bool clearArea)
```
#### Example:
```lua
SetEntityCoords(GetPlayerPedId(), x, y, z, true, false, false, true)
```

### GetEntityHeading:
#### Arguments:
```cpp
int GetEntityHeading(int entity)
```
#### Example:
```lua
GetEntityHeading(GetPlayerPedId())
```

## Gameplay
### GetHashKey:
#### Arguments:
```cpp
int GetHashKey(string modelname)
```
#### Example:
```lua
GetHashKey("SC1")
```

## Streaming
### RequestModel:
#### Arguments:
```cpp
void RequestModel(int hash)
```
#### Example:
```lua
RequestModel(GetHashKey("SC1"))
```

### HasModelLoaded:
#### Arguments:
```cpp
void HasModelLoaded(int hash)
```
#### Example:
```lua
HasModelLoaded(GetHashKey("SC1"))
```

## Stats
### StatSetInt:
#### Arguments:
```cpp
void StatSetInt(int hash, int value, bool save)
```
#### Example:
```lua
StatSetInt(GetHashKey("MP0_CHAR_XP_FM"), 9500, true)
```

### StatSetBool:
#### Arguments:
```cpp
void StatSetBool(int hash, int value, bool save)
```
#### Example:
```lua
StatSetBool((GetHashKey("MPPLY_CHAR_IS_BADSPORT"), 1, true)
```

### StatSetFloat:
#### Arguments:
```cpp
void StatSetFloat(int hash, float value, bool save)
```
#### Example:
```lua
StatSetFloat((GetHashKey("BADSPORT_RESET_MINUTES"), 1.f, true)
```

### StringInputField:
#### Arguments:
```cpp
string StringInputField()
```
#### Example:
```lua
StringInputField() -- return the input
```

## API
### LogConsoleMessage:
#### Arguments:
```cpp
void LogConsoleMessage(string message)
```
#### Example:
```lua
LogConsoleMessage("Hello")
```

### UnloadLuaFile:
#### Arguments:
```cpp
void UnloadLuaFile()
```
#### Example:
```lua
UnloadLuaFile()
```

### StringInputField:
#### Arguments:
```cpp
string StringInputField()
```
#### Example:
```lua
StringInputField() -- returns the input
```

### UnloadLuaFile:
#### Arguments:
```cpp
void APIWait(int ms)
```
#### Example:
```lua
APIWait(2000) --Stop all Scripts for 2000 ms
```

### WriteToMemory:
#### Arguments:
```cpp
void WriteToMemory(DWORD pointer, int value)
```
#### Example:
```lua
WriteToMemory(0x025D6A18 + 0x8DC0EA, 60) 
```

### NotifyMap:
```cpp
void NotifyMap(string message)
```
#### Example:
```lua
NotifyMap("Example") 
```
