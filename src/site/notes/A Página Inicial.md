---
{"dg-publish":true,"permalink":"/A Página Inicial/","tags":["gardenEntry"],"updated":"2025-06-23T20:40:34.268-03:00"}
---

# Hub
>[!cards|dataview 7]
>**[[Caelestis/1. Panteão/1. Panteão\|Deidades]]**
>![gods.jpg](/img/user/gods.jpg)

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
