---
createdOn: <% tp.date.now("dddd, DD-MMM-YYYY") %>
keywords:
---

<%*
const hasTitle = !tp.file.title.startsWith("Untitled");
let title;
if (!hasTitle) {
  title = await tp.system.prompt("Title");
  await tp.file.rename(title);
} else {
  title = tp.file.title;
}
-%>
# <% title %>
<% tp.file.cursor(0) %>
