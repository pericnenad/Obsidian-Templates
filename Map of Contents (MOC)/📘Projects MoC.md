---
tags:
  - MOC
  - projects
---
# Projects Map of Contents

Template: [[Templates/Project]]

```meta-bind-button
label: Create New Project
icon: book-plus
hidden: false
class: ""
tooltip: ""
id: ""
style: primary
actions:
  - type: templaterCreateNote
    templateFile: Templates/Project.md
    folderPath: Projects
    fileName: New Project
    openNote: true

```


The list of 20 recent projects 

```dataview
TABLE file.aliases as Alias, file.cday as Created, summary as Summary, Members
FROM "Projects" AND #projects AND -#MOC
SORT file.name asc LIMIT 20
```
