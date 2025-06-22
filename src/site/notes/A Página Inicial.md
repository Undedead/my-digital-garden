---
{"dg-publish":true,"permalink":"/A Página Inicial/","tags":["gardenEntry"],"updated":"2025-06-22T11:16:46.246-03:00"}
---



# Hub
> [!cards|7]
 **[[📝 Session Note Database\| Session Notes]]**
> ![SessionNotes.png](/img/user/z_Assets/Hub/SessionNotes.png)
>
> **[[🎊Party Database\| Parties]]**
> ![Parties.png](/img/user/z_Assets/Hub/Parties.png)
> 
> **[[🧙‍♂️ Player Database\| Players]]**
> ![Players.png](/img/user/z_Assets/Hub/Players.png)
> 
> **[[🧞‍♀️ Deity Database\| Deities]]**
> ![Deities.png](/img/user/z_Assets/Hub/Deities.png)
> 
> **[[👨‍👩‍👧‍👦 NPC Database\| NPCs]]**
> ![NPCs.png](/img/user/z_Assets/Hub/NPCs.png)
> 
> **[[🔰 Group Database\| Groups]]**
> ![Groups.png](/img/user/z_Assets/Hub/Groups.png)
> 
> **[[🗺️ Kingdoms Database\| Kingdoms]]**
> ![Kingdoms.png](/img/user/z_Assets/Hub/Kingdoms.png)
> 
> **[[🌁 Settlement Database\| Settlements]]**
> ![Settlements.png](/img/user/z_Assets/Hub/Settlements.png)
> 
> **[[🏰Landmark Database\| Landmarks]]**
> ![Landmarks.png](/img/user/z_Assets/Hub/Landmarks.png)
> 
> **[[❓ POI Database\| Points of Interest]]**
> ![POIs.png](/img/user/z_Assets/Hub/POIs.png)
>
> **[[💲 Shop & Service Database\| Shops & Services]]**
> ![ShopsServices.png](/img/user/z_Assets/Hub/ShopsServices.png)
>
> **[[📕 Literature Database\| Literature]]**
> ![Literature.png](/img/user/z_Assets/Hub/Literature.png)
>
> **[[✉️ Letter Database\| Letters]]**
> ![Letters.png](/img/user/z_Assets/Hub/Letters.png)
> 
> **[[❗ Quest Database\| Quests]]**
> ![Quests.png](/img/user/z_Assets/Hub/Quests.png)
> 
> **[[Scratch  Notes\|Scratch  Notes]]**
> ![RandomNotes.png](/img/user/z_Assets/Hub/RandomNotes.png)
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
