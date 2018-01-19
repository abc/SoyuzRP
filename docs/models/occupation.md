# Occupation

[SoyuzRP Documentation - Models](https://abc.github.io/SoyuzRP/models)

An occupation is a character's job, or role. It might be a traditional job, 
such as "Chartered Accountant" or "Police Officer", or it could be a criminal 
position, like "Mafia Consigliere", or something like "Unemployed".

A character's occupation is probably their primary defining characteristic, and 
likely includes a slew of abilities, privileges, prestige and expectations. It 
is therefore important that the most important or impactful occupations are 
given to a server's more experienced, active or well-respected players.

A character can only have one occupation. This is not meant to be an accurate 
depiction of reality, because a character, in real life terms, could hold more 
than one occupation. For example, you could be both a "Mafia Soldato" and a 
"Police Detective", if you were to try and infiltrate the mafia. In these 
instances, the player should be encouraged to choose which of their professions 
is most appropriate to be their 'primary occupation' and use that. 

## Relationships

* A character has one occupation.

## Fields

### id

<dl>
	<dt>Data Type (Lua)</dt>
	<dd>number</dd>

	<dt>Data Type (SQL)</dt>
	<dd>int</dd>

	<dt>SQL options</dt>
	<dd>PK,AI</dd>

	<dt>Description</dt>
	<dd>Primary key for occupation database.</dd>
</dl>

### title

<dl>
	<dt>Data Type (Lua)</dt>
	<dd>string</dd>

	<dt>Data Type (SQL)</dt>
	<dd>varchar</dd>

	<dt>SQL options</dt>
	<dd>None</dd>

	<dt>Description</dt>
	<dd>
		The name of the job position, e.g. Police Detective. Potentially visible 
		to other players.
	</dd>
</dl>

### pay

<dl>
	<dt>Data Type (Lua)</dt>
	<dd>number</dd>

	<dt>Data Type (SQL)</dt>
	<dd>int</dd>

	<dt>SQL options</dt>
	<dd>None</dd>

	<dt>Description</dt>
	<dd>
		The amount of money paid for holding this job position, paid each 
		paycheck. Paycheck duration is variable and determined by the server 
		owner, but is 2 minutes by default.
	</dd>
</dl>