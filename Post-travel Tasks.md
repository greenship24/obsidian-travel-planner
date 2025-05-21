- Essentially this page uses a query to grab tasks from the "Notes" template- add that for each trip and any tasks you have to do after returning will be populated here (and disappear from this list once done)
- This mostly should not have to be modified

#### Tasks from past trips *automatically* aggregated here
 ```tasks
not done
(path does not include templates) AND (path regex matches /202/) AND (filename includes notes)
filter by function task.description.length > 5
sort by urgency
```