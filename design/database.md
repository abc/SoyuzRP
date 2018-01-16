# Player

Players make the game go 'round, and so they're at the top of our database.

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 06 |
| steam_id | string | STEAM_0:1:8422618 |

* TODO: Potentially add administrative rights to this table

# Character

With SoyuzRP, it's possible for a single player to have multiple characters.

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 19 |
| player_id | int | 06 |
| name | string | Jacob Wright |
| occupation_id | int | 23 |

# Occupation

Most characters have jobs. Some are unemployed, or part of a criminal group.

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 23 |
| title | string | Police Detective |
| pay | int | 250 |

* TODO: Consider flags/organisations for API access.

# Item

Characters may have some number of items, such as personal effects or weapons.

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 35 |
| internal_name | string | soyuzcore_atmcard |
| display_name | string | ATM Card |

* An internal name must be unique. We suggest using a common namespace for 
your plugin, like coolguns_colt1911, for a Colt 1911 item added by the "Cool 
Guns" plugin, for example.

# Shop

NPC-owned shops are an important cash sink for the Soyuz economy. 

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 40 |
| display_name | string | Downtown Guns n Ammo |
| position_x | double | 495.21 |
| position_y | double | -112.60 |
| position_z | double | 50.32 |
| display_model | string | citizen02.mdl |

* TODO: Investigate how models/NPCs could be implemented technically.

# Door

Characters and organisations have doors which they need to lock and unlock. 

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 54 |
| ent_id | int | 555 |
| display_name | string | Jail Cell 3 |

* TODO: Look into how doors work internally - are they entity IDs like I 
	expect them to be, or are they a little different in Source?

# Property

Properties are, essentially, a collection of doors grouped as a cohesive unit.

A door can not be part of two properties at the same time.

| Name | Type | Sample |
| ---- | ---- | ------ |
| id | int | 62 |
| owner_id | int | 19 |
| display_name | string | Police Department |