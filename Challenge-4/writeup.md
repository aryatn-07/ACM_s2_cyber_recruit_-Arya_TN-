CHALLENGE DESCRIPTION:
An image was recovered from an offline archaeological dataset dated before 2005.
The structure shown in the image does not cast a clear shadow, despite being outdoors.

The image contains:
Repeating stone stair geometry
No inscriptions
No visible water
No people
No sky

You are told only this:

“Built to defeat heat, not enemies.”

Objectives

Identify:

1. name of the structure

2. state which this exists

Flag Format

flag{structure_name|state_name}

ANALYSIS/APPROACH:
Searched the image on Google images and got Chand Baori in Rajasthan as the result.Tried different variations of it as the flag but it didnt work. Then tried out  other stepwells which fit the description which was also incorrect. As there was no progress, tried if the image contained any hidden text by using the 'cat image.jpeg' and checked if there was any hidden strings using the command 'strings image.jpeg', but found nothing.Next I checked for the existance of any embedded files in the image using 'binwalk image.jpeg' which was also futile.As there were no results, went back to trying out different case variations of the reverse image search result obtained first to get the final flag.

TOOLS USED: Google Images

COMMANDS USED: cat image.jpeg, strings image.jpeg, binwalk image.jpeg

Flag: flag{chand_baori|Rajasthan}
