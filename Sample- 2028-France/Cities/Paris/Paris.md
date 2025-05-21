---
banner: "https://lostinfrenchlation.com/wp-content/uploads/2018/06/paris-champs-elysees.jpg"
banner_y: 0.12
banner_lock: true
---
### Itinerary
```dataview
TABLE 
  date as "Date",
  place as "Place",
  start as "Start Time",
  end as "End Time"
SORT date ASC, start ASC
FLATTEN date
WHERE itinerary AND !contains(file.name, "Event template") AND !contains(file.name, "Flight template") AND date AND this.file.path AND contains(place, this.file.name)
```

```folder-overview
id: f0a888c8-adb6-412e-bac7-e396b66a7914
folderPath: ""
title: "{{folderName}} overview"
showTitle: true
depth: 3
includeTypes:
  - folder
  - markdown
style: list
disableFileTag: false
sortBy: name
sortByAsc: true
showEmptyFolders: false
onlyIncludeSubfolders: false
storeFolderCondition: true
showFolderNotes: false
disableCollapseIcon: true
```

### Links
- 

### Tasks
- [ ] This is a task on the folder overview for Paris- check train times

### Map
```mapview
{"name":"Default","mapZoom":8,"centerLat":48.8582599,"centerLng":2.2945006,"query":"","chosenMapSource":0,"autoFit":false,"lock":false,"showLinks":false,"linkColor":"red","markerLabels":"off","embeddedHeight":300}
```
