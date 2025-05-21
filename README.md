# Obsidian Travel Planner

This is not a plugin but rather a base vault that you can extend (or just pick from to add to your existing vault, etc.)

#### Required
- Obsidian
- [Dataview plugin](https://github.com/blacksmithgu/obsidian-dataview)
- [Map View plugin]([https://github.com/esm7/obsidian-map-view](https://github.com/esm7/obsidian-map-view))
- [Meta Bind plugin]([https://github.com/mProjectsCode/obsidian-meta-bind-plugin](https://github.com/mProjectsCode/obsidian-meta-bind-plugin))
- [Tasks plugin](https://github.com/obsidian-tasks-group/obsidian-tasks)
- Obsidian sync, syncthing, remotely save or something else
- [List Callouts plugin](https://github.com/mgmeyers/obsidian-list-callouts) - for easy color coding/icons of certain sections of the templates
#### Recommend plugins
- [Auto Link Title](https://github.com/zolrath/obsidian-auto-link-title) - pasting links and getting page titles automatically makes things so much easier
- [Auto Note Mover](https://github.com/farux/obsidian-auto-note-mover) - move notes where they need to be by adding a simple tag
- [Automatic Table of Contents](https://github.com/johansatge/obsidian-automatic-table-of-contents) - adds a ToC to any page- useful for folder notes and elsewhere
- [Banners](https://github.com/noatpad/obsidian-banners) - class up your event/place notes with a picture
- [Folder Notes](https://github.com/LostPaul/obsidian-folder-notes) - used to add a note and table of contents to main trip folder
- [Linter](https://github.com/platers/obsidian-linter) - keeps it clean, especially with multiple editors
- [Mermaid Tools](https://github.com/dartungar/obsidian-mermaid) - can be nice if you like travel flow charts
- [Paste image rename](https://github.com/reorx/obsidian-paste-image-rename)- absolutely a must for me- cleans up pasted image names when they’re uploaded
- [Style Settings](https://github.com/mgmeyers/obsidian-style-settings) – very much personal preference
- [Tag Wrangler](https://github.com/pjeby/tag-wrangler) - I’ve found myself wanting to change an entire tag at times and this makes it easy to update everywhere

### Overview
In general, you can lay it out how you like and what works but I have a few “core” ideas of how I structured it personally.

```

YYYY-<TripName>
- <city> folder for each city you plan on visiting (disregard if there is only one)
- Food and Drinks subfolder (for all restaurants, bars, wineries, etc.)
- Itinerary note (auto updating via dataview)
- Map (either one note or multiple notes or a folder full of notes with a map view)
- Tasks note (aggregates all tasks throughout the trip folder in one easy to use note)
- Transit folder (ie. taking multiple trains, use the transit template)
Templates folder (in root folder by default and these can be modified however you like before starting)

```

### Usage
First off, most notes will use templates. Someone could probably fix up some templater template that places the skeleton of a trip folder together in one quick go.

#### Prep work
- Create different icons for mapview plugin ([https://github.com/esm7/obsidian-map-view?tab=readme-ov-file#marker-icons](https://github.com/esm7/obsidian-map-view?tab=readme-ov-file#marker-icons))
- this step only needs done once (will work for all subsequent trips)
- add these to the meta bind plugin with an INPUT selector for your tags
- This is done by going into the plugin settings and updating/adding the templates- New icons need updated only in TWO areas (map view plugin settings and meta bind plugin settings) and it will automatically be available to ALL notes, past and present (we try to keep it DRY here)
- Create your trip folder- ie. 2028- Paris
- Create auto-move configs in the plugin settings
	- ie. ^paris , use regex, move to 2028-France/Paris
	- ^paris\/.* , use regex, move to 2028France/Paris/Food and Drink
	- NOTE- "use regex" toggle must be turned to on in the plugin settings for the above to work
- modify all for your use (and whatever folder you want them dropped in)
#### Vacation building
- Create a new note with the title (ie. Eiffel Tower)
- Use command palette (ctrl+p generally or swipe down on mobile), insert template
- pick a template
- The inline mapview is near the top- select this and insert a single space after the title to get it to search for your landmark/restaurant, etc.
- Pick the appropriate selection and then go to the end of this line, then select a category from the dropdown to “customize” the icon that appears on the map
- Fill out the rest of the template as you need (add links to the wikipedia, a link to where you buy tickets, common tourist info, etc.)
- Add a tag that you have customized in Auto Note Mover to move it to the proper folder automatically
	- NOTE- this currently “unloads” the meta bind buttons/inputs- simply close the note and reopen to get them working again- Unsure how to fix this or if possible
- Any tasks added here are automatically added to the overall “Tasks” template in your trip folder and completing it on EITHER page will mark it complete on both pages
- Use the itinerary section to select date, place (can be city, neighborhood, whatever), start and end times
- Click “Add to itinerary” to have it set on the Itinerary note OR “remove” to obviously remove
	- NOTE- You *must* select a date for the Add button to have any effect (the dataview query makes sure each note has a date or else it will not be included in the results)
	- Place and times are optional but recommended as the query categorizes based first on date and then on start time
	- I don’t quite recall if it matters for dataview but I put dates in ISO8601 format (YYYY-MM-DD) and times in hh:mm format, place simply refers to city (or more/less specific- this is user preference)

### Overall template design
- Geo location (via Map View plugin) and tags are at the top. These are vitally important as they determine how your itinerary and such update. Also if your item shows up on the map and how (ie. use a geo location link and then add a tag to style the icon that represents it on the map)
- Information- general info about the flight/restaurant/site, etc.
- Hours and pricing (event/site only)- used with List Callouts plugin above to put the most important info (like pricing, hours of operation, duration needed, etc.) in bold, bright colors.
- Attachments- PDFs of flight itineraries or hotel reservations can go here
- Links- links about the site, more info, etc.
- Tasks- Add tasks here so you can keep them associated with the actual event/item needing attention but they will be linked in a big list on the “Tasks” note so you can have an overall view of what all still needs done (this limits itself to ONLY the trip it is present in FYI)

#### Templates in sample vault
- Drinks- simple bar/brewery/winery, etc.
- Event (or site)- generic template used for any attractions/sites/places that aren’t food related
- Flight- use in root of trip folder to organize flight details
- Folder Overview- use on/in your city-specific subfolders
	- MUST have Folder Notes plugin to use
	- ie. if you are traveling to Paris, Lyon, Marseille make a folder for each one and then add this folder note template to each of those cities to give you an overview of everything inside of each
- Hotel- aggregate all hotel details (can use in subfolders or in root of trip folder)
- Itinerary- gives you an itinerary from your notes assuming you follow instructions under “Vacation building” above
	- NOTE- this template *never* needs modified to display your itinerary so long as it is in the root of your specific trip
- Miscellaneous- a catch all to put random info that doesn’t fit elsewhere
- Packing list- optional template to put in your trip root to bring whatever along with you, useful to customize this template with items you always carry and add trip-specific items as well
- Rental- If you are renting a car you can use this and put the info there
- Tasks- Aggregates all tasks in your trip on one easy to view page
	- NOTE- this template *never* needs modified to display the tasks under your trip folder
- Transit- Used to aggregate all transit info (ie. train plans, ticket info, etc.)
#### Default tags
These were just helpful for me personally to find info throughout the vault
- hotel
- flight
- transit
- mustsee (for those places you must go to while in town)
#### Bonus tips
- I recommend adding more “Open in…” in the settings in Mapview like open in OSM, Waze, etc.
- Along with that, I *highly* recommend reading esm7’s sterling docs at the mapview github repo and adding more maps (free or paid) alongside the default CartoDB (I’ve found transport ones to be highly valuable to figure out a path from one place to another quickly without having to use a different mapping solution
- You *can* modify the restaurant/bar templates to discard itinerary items. I generally do not really schedule stops at certain restaurants or bars but figured I’d include them for people anyhow.
- Maybe make 2 vaults by default- as you do the trip then simply cut/paste the folder to the “trip archive” vault to keep your primary travel planner from getting too heavy
- I think you can see how you can extend this- ie. copy the “Drinks” template and make a coffee one with a different icon by default, etc. I like the dropdown to stop having so many templates but it’s whatever you want-ie. Extensible.

#### Opinionated?

I find it useful to note this is *somewhat* opinionated. I tried to not lock things in precisely the way I do it in my own travel vault but some things I did make opinionated. For instance- meta bind plugin is necessary *and* I use it to set tags for the whole note. What this means is your icon will be whatever is selected in those tags and if you have two locations on one note then they both have the same icon. I have not yet talked to esm7 (dev of mapview) to work a better way of tagging as I could not find a way to set it in the style of tag:<tag> as per the mapview docs and have it be easily customizable. Other things in the vault are also opinionated (ie. how you tag things define if they end up in another note, etc. via the dataview or tasks queries, etc.) I think it’s near impossible to have it be fully usable but not opinionated to an extent.

To that end, I highly encourage people to view this as a “template vault” and either start from it OR just use inspiration from it. I don’t intend to really “maintain” it so much as make sure it continues being a good jumping off point, regardless of how you tweak it. I have other obligations (family, work, etc.) so consistently updating this is not really in my plans (though if I find useful updates I will make them or if you submit a PR I’ll take a gander.)

### Special thanks to
Newton said it- we stand on the shoulders of giants. Thanks (and donations are welcome I’m sure) to the people behind the following projects (all links go to their donations page):
- Obsidian - [https://obsidian.md/pricing](https://obsidian.md/pricing) for donations or subscription for easy syncing
- Dataview- [https://github.com/blacksmithgu/obsidian-dataview](https://github.com/blacksmithgu/obsidian-dataview)
- Map View - [https://github.com/esm7/obsidian-map-view?tab=readme-ov-file](https://github.com/esm7/obsidian-map-view?tab=readme-ov-file)
author has his/her own guide here which I built upon (thanks!)- [https://forum.obsidian.md/t/planning-a-vacation-with-map-view/43613](https://forum.obsidian.md/t/planning-a-vacation-with-map-view/43613)
- Meta Bind- Did not find a donation link but THANK YOU DEVS
- Tasks- [https://github.com/sponsors/claremacrae](https://github.com/sponsors/claremacrae)
- List Callouts- [https://www.buymeacoffee.com/mgme](https://www.buymeacoffee.com/mgme)
- Auto note mover - [https://github.com/farux/obsidian-auto-note-mover](https://github.com/farux/obsidian-auto-note-mover)
- Auto Link Title- Did not find a donation link but THANK YOU DEVS
- Automatic Table of Contents- Did not find a donation link but THANK YOU DEVS
- Banners- Did not find a donation link but THANK YOU DEVS
- Folder Notes- https://ko-fi.com/D1D1GHGSI
- Linter- [https://github.com/platers/obsidian-linter#how-you-can-help](https://github.com/platers/obsidian-linter#how-you-can-help) No donations but you can help (in many ways) by fixing docs, reporting bugs, etc.
- Mermaid JS- No donation link found but THANK YOU DARTUNGAR
- Paste Image Rename- Did not find a donation link but THANK YOU DEVS
- Style Settings- [https://www.buymeacoffee.com/mgme](https://www.buymeacoffee.com/mgme) This is made by the same dev as List Callouts so if you wish to donate you can do so once to cover both
- Tag Wrangler- no donation link found but THANK YOU PJEBY

All donation links simply found from the respective projects’ github pages. If you wish, just navigate to those (at the top) and then follow the links yourself.
