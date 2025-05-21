```table-of-contents
```

### Overall Itinerary
```dataview
TABLE 
  date as "Date",
  place as "Place",
  start as "Start Time",
  end as "End Time"
SORT date ASC, start ASC
FLATTEN date
WHERE itinerary AND !contains(file.name, "Event template") AND !contains(file.name, "Flight template") AND date AND contains(file.path, this.file.folder)
```



### Daily itinerary below
```dataview
TABLE 
  date as "Date",
  place as "Place",
  start as "Start Time",
  end as "End Time"
SORT date ASC
FLATTEN date
WHERE itinerary AND date = date(today) AND !contains(file.name, "template") AND contains(file.path, this.file.folder)
```

### Tomorrow's Itinerary
```dataview
TABLE 
  date as "Date",
  place as "Place",
  start as "Start Time",
  end as "End Time"
SORT date ASC
FLATTEN date
WHERE itinerary AND date = date(tomorrow) AND !contains(file.name, "template") AND contains(file.path, this.file.folder)
```

### Day after tomorrow itinerary
```dataview
TABLE 
  date as "Date",
  place as "Place",
  start as "Start Time",
  end as "End Time"
FROM #itinerary  
SORT date ASC
FLATTEN date
WHERE itinerary AND date = (date(tomorrow) + dur(1 day)) AND !contains(file.name, "template") AND contains(file.path, this.file.folder)
```

