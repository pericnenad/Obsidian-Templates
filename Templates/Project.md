<%*
	let project_name = await tp.system.prompt("Project Name")
	let alias = await tp.system.prompt("Short Name / Acronym")
	let team = await tp.system.prompt("Team") || "Default Project Name"
	let summary =  await tp.system.prompt("Short Summary") || "Fill in the Project Summary"
-%>
---
company: MyCompany
summary: <%summary%>
aliases: 
 - <%alias%>
tags:
 - projects
team: <%team%>
---
<% await tp.file.move("/Projects/" + project_name) %>
# [[<% project_name %>]]
### <%alias%>

