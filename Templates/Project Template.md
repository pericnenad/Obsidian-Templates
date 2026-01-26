<%*
	let project_name = await tp.system.prompt("Project Name")
	let alias = await tp.system.prompt("Short Name / Acronym")
	let team = await tp.system.prompt("Team") || "My Team"
	let summary =  await tp.system.prompt("Short Summary") || "Fill in the Project Summary"
	const created_on = tp.date.now("dddd, DD-MMM-YYYY");
-%>
---
company: your_company
summary: <%summary%>
aliases: 
 - <%alias%>
tags:
 - projects
team: <%team%>
date: <% tp.file.creation_date() %>
year: <% tp.date.now("YYYY") %>
quarter: <% tp.date.now("[Q]Q") %>
type: project
createdOn: <% created_on %>

---

<% await tp.file.move("/Projects/" + project_name) %>
# [[<% project_name %>]]
## <%alias%>


