---
date: <% tp.file.creation_date() %>
type: 1x1
company: MyCompany
summary: " "
tags:
  - meeting
---
tags:: [[📅Meetings MOC]]
Date: [[<% tp.date.now("DD-MMM-YYYY, dddd") %>]]
<% await tp.file.rename(tp.file.title + " " + tp.date.now("DD-MMM-YYYY")) %>
# [[<% tp.file.title + " " + tp.date.now("DD-MMM-YYYY") %>]]

**Attendees**: [[ ]] 

## Agenda/Questions
- 

## Notes / Links
- 

## Next Steps / Action Items
- 