# SoyuzRP Documentation - Database Structure

[SoyuzRP Documentation - Index](https://abc.github.io/SoyuzRP)

This document is a draft, proposal or work-in-progress. It is likely to be 
subject to rapid and drastic changes. 

**Entity Tables**

If a database table is enabled as an entity, then additional data can be stored 
about the entity in the "data" table for that type. For example, you could 
store details about donator status in the player_data table, because players 
are marked as entity types.

## player

Players make the game go 'round, and so they're at the top of our database.

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 06 |
| steam_id | string | STEAM_0:1:8422618 |

### player_data

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 95 |
| player_id | int | 06 |
| data_key | string | "soyuzcore.donator_level" |
| data_value | string | "VIP" |


* Players are entity types.
* TODO: Potentially add administrative rights to this table


## character

With SoyuzRP, it's possible for a single player to have multiple characters.

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 19 |
| player_id | int | 06 |
| name | string | Jacob Wright |
| occupation_id | int | 23 |

### character_data

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 95 |
| character_id | int | 19 |
| data_key | string | "soyuzcore.age" |
| data_value | string | "23" |

* Characters are entity types.

## occupation

Most characters have jobs. Some are unemployed, or part of a criminal group.

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 23 |
| title | string | Police Detective |
| pay | int | 250 |

### occupation_data

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 95 |
| occupation_id | int | 23 |
| data_key | string | "soyuzcore.scoreboard_color" |
| data_value | string | "#0000ff" |

* Occupations are entity types.

## item

Characters may have some number of items, such as personal effects or weapons.

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 35 |
| internal_name | string | soyuzcore.atmcard |
| display_name | string | ATM Card |
| on_use | string | soyuz_useatm |

### item_data

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 95 |
| item_id | int | 35 |
| data_key | string | "soyuzcore.drops_when_killed" |
| data_value | string | "true" |

* Items are entity types.

* The `on_use` field is used to run a command when the item is used.

* An internal name must be unique. We suggest using a common namespace for 
your plugin, like coolguns.colt1911, for a Colt 1911 item added by the "Cool 
Guns" plugin, for example.

## door

Characters and organisations have doors which they need to lock and unlock. 

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 54 |
| ent_id | int | 555 |
| display_name | string | Jail Cell 3 |

* TODO: Look into how doors work internally - are they entity IDs like I 
	expect them to be, or are they a little different in Source?

* TODO: Does door need to be an entity type?

## property

Properties are, essentially, a collection of doors grouped as a cohesive unit.

A door can not be part of two properties at the same time.

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 62 |
| owner_id | int | 19 |
| display_name | string | Police Department |

### property_data

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 95 |
| property_id | int | 62 |
| data_key | string | "soyuzcore.occupation_flags" |
| data_value | string | "soyuzcore.is_police" |


* Properties are entity types.

## audit_history

All database interactions should be tracked in this table for troubleshooting.

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 32 |
| target_type | string | character |
| target_fields | string | occupation_id |
| new_value | string | 23 |
| updated_id | int | 19 |
| updated_by | int | 06 |
| detail | string | 
| source | string | soyuzcore |
| date_updated | datetime | 2017-01-01 05:23:14 |