<%*
	let meeting_name = await tp.system.prompt("Name of the Meeting")
	let meeting_type = await tp.system.prompt("Type (scrum, 1x1, etc..)[1x1]") || "1x1"
	const fileName = meeting_name + " " + tp.date.now("DD-MMM-YYYY")
	const existing = tp.file.find_tfile(fileName);
-%>
---
date: <% tp.file.creation_date() %>
type: <% meeting_type %>
company: Your Company
summary: <% meeting_type %> <% meeting_name %> <% tp.date.now("DD-MMM-YYYY") %>
tags: meeting
---

Date: [[<% tp.date.now("DD-MMM-YYYY, dddd") %>]]
<% await tp.file.move("Meetings/" + meeting_type +" "+ meeting_name + "-" + tp.date.now("DD-MMM-YYYY")) %>
# [[<% meeting_type +" "+ meeting_name + " " + tp.date.now("DD-MMM-YYYY") %>]]

**Attendees**: [[ ]] 

## Agenda/Questions
- 

## Notes 
- 

## Next Steps / Action Items
- 
## Links
- 
## Recent Meetings of this type
```dataview
TABLE file.cday as Created, summary
FROM "Meetings" and -#MOC
WHERE lower(type) = lower("<%meeting_type%>") AND file.ctime >= date(today) - dur(30 days) AND file.name != this.file.name
SORT file.cday DESC
LIMIT 5
```
