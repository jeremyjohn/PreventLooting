**Prevent Looting** provides protection for entity of player (boxes, furnaces, careers, etc.) from looting by other players. Ideal for PVE servers, but can be used for PVP. The plugin supports in-game teams, FriendsAPI, ZoneManager and permissions.

You can configure the plugin to work only in the range of the cupboard or not. And all who will be authorized in the cupboard will have the opportunity to loot.

*Attention:** When anyone try to loot sleeper, his inventory will open, but did not open sleeper inventory, because so the hook of Oxide works - it prevents the opening of the inventory of another player, but did not prevent sending of the RPC to the client.

## Dependencies

### Optional

- [Backpacks](https://oxidemod.org/plugins/backpacks.1408/)
- [Friends API](https://oxidemod.org/plugins/friends-api.686/)
- [Zones Manager](https://oxidemod.org/plugins/zones-manager.739/)

Using **Friends API** allows you to allow your friends access to your entities. Using **Zone Manager** allows you to disable the plugin in certain zones.

## Permissions

- **preventlooting.use** -- Permission to use commands
- **preventlooting.player** -- Prevents looting of a player thats having permission
- **preventlooting.corpse** -- Prevents looting of a corpse of a player thats having permission
- **preventlooting.backpack** -- Prevents looting of a backpack of a player thats having permission
- **preventlooting.storage** -- Prevents looting of a storage of a player thats having permission
- **preventlooting.admin** -- For admins and moderators, duplicating the option "AdminCanLoot" in the config for use without the privileges of the admin

## Chat commands

If you want to share an entity with other players, you can use chat commands. To use commands, you need to look at your entity.

- **/share** -- Allow access to all players
- **/share `<username>`** -- Allow access only to certain players
- **/unshare** -- Deny access from all players
- **/unshare `<username>`** -- Deny access to specific players only
- **/sharelist** -- List of permissions for the entity
- **/shareclear** -- Clear the list of permissions for the entity
- **/checkit** -- Checking loot protection

## Configuration

**AdminCanLoot** - allows the administrator to open any entity

**CanLootCorpse** - allows loot corpses

**CanLootEntity** - allows loot entities

**CanLootPlayer** - allows loot players

**CanLootBackpack** - allow loot backpacks

**CanLootBackpackPlugin** - allow loot backpacks from plugin Backpacks

**CanPickup** - allow pickup elements of construction and decoration (doors, windows, decor, etc)

**UseCupboard** - enable to share entities if cupboard authorization, in cupboard radius

**UseCupboardInclude** - list of types to loot with parameter UseCupboard. Types available: storage, player, corpse, backpack, backpackplugin. The default value is recommended. Note: with "UseCupboardInclude" values: player, corpse, backpack, backpackplugin - allowing loot only when both player auth in cupboard!

**UseOnlyInCupboardRange** - enable to use the plugin only in the coverage area of cupboard

**UseOnlyInCupboardRangeInclude** -  list of types to loot with parameter UseOnlyInCupboardRange. Types available: storage, player, corpse, backpack, backpackplugin. The default value is recommended.

**ExcludeEntities** - list of excludes

**UseExcludeEntities** - enable to use of excludes list

**UseFriendsAPI** - enable to use Friends API

**UseTeams** - enable to use in-game teams

**UsePermission** - enable to use permissions

**UseZoneManager** - enable to use the Zone Manager to exclude the plugin from working in a certain zone

**ZoneManagerIncludeMode** - enable to exclude plugin in all zones and use "ZoneID" list to include the plugin to working in a certain zone

**ZoneID** - list of zones in which the plugin will be included or excluded

### Default Configuration

```json
{
  "AdminCanLoot": true,
  "CanLootBackpack": false,
  "CanLootBackpackPlugin": false,
  "CanLootCorpse": false,
  "CanLootEntity": false,
  "CanLootPlayer": false,
  "CanPickup": false,
  "ExcludeEntities": [
    "mailbox.deployed"
  ],
  "UseCupboard": false,
  "UseCupboardInclude": [
    "storage"
  ],
  "UseExcludeEntities": true,
  "UseFriendsAPI": true,
  "UseOnlyInCupboardRange": false,
  "UseOnlyInCupboardRangeInclude": [
    "storage"
  ],
  "UsePermission": false,
  "UseTeams": true,
  "UseZoneManager": false,
  "ZoneID": [
    "12345678"
  ],
  "ZoneManagerIncludeMode": false
}
```

## Default Language

The default messages are in the `PreventLooting.json` file under the `oxide/lang/en` directory. To add support for another language, create a new language folder (ex. de for German) if not already created, copy the default language file to the new folder, and then customize the messages. Support is also available for Russian by default.
