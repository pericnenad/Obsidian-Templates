<%*
	let meeting_name = await tp.system.prompt("Name of the Meeting")
	let meeting_type = await tp.system.prompt("Type (scrum, 1x1, something else)")
-%>
---
date: <% tp.file.creation_date() %>
type: <% meeting_type %>
company: Red Hat
summary: " "
tags: meeting
---

tags:: [[📅Meetings MOC]]
Date: [[<% tp.date.now("DD-MMM-YYYY, dddd") %>]]
<% await tp.file.rename(meeting_name + " " + tp.date.now("DD-MMM-YYYY")) %>
# [[<% meeting_name + " " + tp.date.now("DD-MMM-YYYY") %>]]

**Attendees**: [[ ]] 

## Agenda/Questions
- 

## Notes / Links
- 

## Next Steps / Action Items
- 

## Recent Meetings of this type
```dataview
TABLE file.cday as Created, summary
FROM "Meetings" and -#MOC
WHERE lower(type) = lower("<%meeting_type%>") AND file.ctime >= date(today) - dur(10 days) AND file.name != this.file.name
SORT file.cday DESC
LIMIT 5
```
