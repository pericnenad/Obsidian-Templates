<%*
	let person_name = await tp.system.prompt("Person's Full Name")
	let alias = await tp.system.prompt("Short Name / Alias")
	let title = await tp.system.prompt("Title")
	let team = await tp.system.prompt("Team")
	let location = await tp.system.prompt("Location")
-%>
---
company: MyCompany
location: <%location%>
title: <%title%>
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

## Meetings in the past month
```dataview
TABLE file.cday as Created, summary AS "Summary"
FROM "Meetings" where contains(file.outlinks, this.file.link) AND file.mtime >= date(today) - dur(1 month)
SORT file.cday DESC
```