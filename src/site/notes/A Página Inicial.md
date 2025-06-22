---
{"dg-publish":true,"permalink":"/A Página Inicial/","tags":["gardenEntry"],"updated":"2025-06-22T11:16:46.246-03:00"}
---



# Hub
> [!cards|7]
 **[[📝 Session Note Database\| Session Notes]]**
> ![[SessionNotes.png\|SessionNotes.png]]
>
> **[[🎊Party Database\| Parties]]**
> ![[Parties.png\|Parties.png]]
> 
> **[[🧙‍♂️ Player Database\| Players]]**
> ![[Players.png\|Players.png]]
> 
> **[[🧞‍♀️ Deity Database\| Deities]]**
> ![[Deities.png\|Deities.png]]
> 
> **[[👨‍👩‍👧‍👦 NPC Database\| NPCs]]**
> ![[NPCs.png\|NPCs.png]]
> 
> **[[🔰 Group Database\| Groups]]**
> ![[Groups.png\|Groups.png]]
> 
> **[[🗺️ Kingdoms Database\| Kingdoms]]**
> ![[Kingdoms.png\|Kingdoms.png]]
> 
> **[[🌁 Settlement Database\| Settlements]]**
> ![[Settlements.png\|Settlements.png]]
> 
> **[[🏰Landmark Database\| Landmarks]]**
> ![[Landmarks.png\|Landmarks.png]]
> 
> **[[❓ POI Database\| Points of Interest]]**
> ![[POIs.png\|POIs.png]]
>
> **[[💲 Shop & Service Database\| Shops & Services]]**
> ![[ShopsServices.png\|ShopsServices.png]]
>
> **[[📕 Literature Database\| Literature]]**
> ![[Literature.png\|Literature.png]]
>
> **[[✉️ Letter Database\| Letters]]**
> ![[Letters.png\|Letters.png]]
> 
> **[[❗ Quest Database\| Quests]]**
> ![[Quests.png\|Quests.png]]
> 
> **[[Scratch  Notes\|Scratch  Notes]]**
> ![[RandomNotes.png\|RandomNotes.png]]
>

## To Do
> [!column|2 no-title]
>> [!metadata] Short Term
>
>
>> [!metadata] Long Term
>
>

## Random Notes
> [!cards|dataview 7] **Party**
>```dataview
> TABLE WITHOUT ID
>     "<span style='display: block; text-align: center; margin-bottom: 5px;'>" + link(file.link, Title) + "</span>" AS Title,
>	embed(art) AS "Art"
> WHERE contains(NoteIcon, "Character") OR contains(NoteIcon, "Settlement") OR contains(NoteIcon, "Deity") OR contains(NoteIcon, "Kingdom") OR contains(NoteIcon, "Landmark") OR contains(NoteIcon, "POI") OR contains(NoteIcon, "Shop") OR contains(NoteIcon, "Group") OR contains(NoteIcon, "Literature") OR contains(NoteIcon, "Letter") OR contains(NoteIcon, "Quest") OR contains(NoteIcon, "SideQuest")
FLATTEN [ [(seed) => (seed * 1103515245 + 12345) % 2147483648]] AS random
FLATTEN [number(dateformat(date("now"), "x"))] AS seed
SORT random[0](seed + file.size)
LIMIT 14
