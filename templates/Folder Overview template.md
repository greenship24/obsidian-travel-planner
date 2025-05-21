### Itinerary
```dataview
TABLE 
  date as "Date",
  place as "Place",
  start as "Start Time",
  end as "End Time"
FROM #itinerary 
SORT date ASC, start ASC
FLATTEN date
WHERE !contains(file.name, "Event template") AND !contains(file.name, "Flight template") AND date AND this.file.path AND contains(place, this.file.name)
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
- [ ] 

### Map