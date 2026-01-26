<%*
	let person_name = await tp.system.prompt("Person's Full Name")
	let alias = await tp.system.prompt("Short Name / Alias")
	let title = await tp.system.prompt("Title")
	let team = await tp.system.prompt("Team")
	let location = await tp.system.prompt("Location")
	let manager = await tp.system.prompt("Manager (if known)")
-%>
---
company: your_company
location: <%location%>
title: <%title%>
manager: <%manager%>
email: 
aliases: 
 - <%alias%>
tags:
 - person
team: <%team%>
---
tags:: [[👥 People MOC]]
<% await tp.file.move("/People/" + person_name) %>
# [[<% person_name %>]]

## Notes and Links
- 

## 1x1 Meetings in the past month
```dataview
TABLE file.cday as Created, summary AS "Summary"
FROM "Meetings" where contains(file.outlinks, this.file.link) AND file.mtime >= date(today) - dur(1 month) AND type = "1x1"
SORT file.cday DESC
```
## Other Meetings in the past month
```dataview
TABLE file.cday as Created, summary AS "Summary"
FROM "Meetings" where contains(file.outlinks, this.file.link) AND file.mtime >= date(today) - dur(1 month) AND type != "1x1"
SORT file.cday DESC
```
