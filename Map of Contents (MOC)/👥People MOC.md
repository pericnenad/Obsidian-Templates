# 👥People MOC
#MOC

```meta-bind-button
label: Create New Person
icon: user-plus
hidden: false
class: ""
tooltip: "Create New Person Note"
id: ""
style: primary
actions:
  - type: templaterCreateNote
    templateFile: Templates/People Template.md
    folderPath: People
    fileName: Enter Name
    openNote: true

```
# People - Map Of Contents
 People Notes are about jotting down notable information about people and linking people back to [[📅Meetings MOC]].

---
### Templates
- [[People Template]]
# People

## Managers

```dataview
TABLE location as Location, team as Team
FROM "People"
WHERE contains(lower(title), "manager")
```
## Everyone

```dataview
TABLE  title, location, team
FROM  "People"
SORT file.name ASC
```