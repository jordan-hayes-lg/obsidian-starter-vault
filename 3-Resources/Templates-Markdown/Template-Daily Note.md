<%*
let date = tp.date.now('YYYY-MM-DD')
_%>
<%"---"%>
created: <% date %>
tags: daily_note
<%"---"%>

# <% tp.date.now("dddd, MMMM DD, YYYY") %>

```dataviewjs  
let current = dv.current()  
let currentDay = current.file.day  
let prev = dv  
.pages("#daily_note")  
.where(x => x.file.day < currentDay)  
.sort(x => x.file.day)  
.values.slice(-1)[0]  
let next = dv  
.pages("#daily_note")  
.where(x => x.file.day > currentDay)  
.sort(x => x.file.day)  
.values[0]  
dv.span("<- ")  
dv.span(prev.file.link)  
if (next) {  
dv.span(" | ")  
dv.span(next.file.link)  
dv.span(" ->")  
}  
```


## Goal To-Dos
- [ ] push-ups
- [ ] sit-ups
- [ ] stretch
- [ ] read 10 pages
- [ ] Make Bed

## Work To-Dos #work
- [ ] 


## Outstanding Work To Do
```tasks
not done
tags include #work 
```

## Open Projects
```dataview
LIST
FROM #open-ongoing-project
SORT file.name ASC
```

## Files I Touched Today

```dataview
TABLE file.ctime as Created, file.mtime as Modified
WHERE file.cday = this.file.day OR file.mday = this.file.day
SORT file.mtime DESC
```
# Daily Notes


# Important Meetings

