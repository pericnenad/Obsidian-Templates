# 📅Meetings MOC

%% Tag search:: #MOC %% 
# Meetings MOC

**Template:** [[Meeting Template]]

```meta-bind-button
label: New Meeting
icon: calendar-plus
hidden: false
class: ""
tooltip: "Create a New Meeting Note"
id: ""
style: primary
actions:
  - type: templaterCreateNote
    templateFile: Templates/Meeting Template.md
    folderPath: Meetings
    fileName: ChangeName
    openNote: true

```

- [1 on 1 Meetings in the last 10 days](#1%20on%201%20Meetings%20in%20the%20last%2010%20days)
- [Managerial Meetings in the last 10 days](#Managerial%20Meetings%20in%20the%20last%2010%20days)
- [Scrums and Standups in the last 10 days](#Scrums%20and%20Standups%20in%20the%20last%2010%20days)


### Scrums and Standups in the last 10 days

```dataview
TABLE file.cday as Created, summary
FROM "Meetings" and -#MOC
WHERE lower(type) = "scrum" OR type = "standup" AND file.ctime >= date(today) - dur(10 days)
SORT file.cday DESC
LIMIT 10
```

### Managerial Meetings in the last 10 days

```dataview
TABLE file.cday as Created, summary
FROM "Meetings" and -#MOC
WHERE lower(type) = "managerial" AND file.ctime >= date(today) - dur(10 days)
SORT file.cday DESC
```

### 1 on 1 Meetings in the last 10 days

```dataview
TABLE file.cday as Created, summary
FROM "Meetings" and -#MOC
WHERE type = "1x1" AND file.mtime >= date(today) - dur(10 days)
SORT file.cday DESC
```
