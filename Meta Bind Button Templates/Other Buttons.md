label: New Meeting
icon: calendar-plus
class: ""
tooltip: Create a New Meeting Note
id: new_meeting
style: primary
hidden: false
actions:
  - type: templaterCreateNote
    templateFile: Templates/Meeting Template.md
    folderPath: Meetings
    fileName: ChangeName
    openNote: true

label: Create New Person
icon: user-plus
hidden: false
class: ""
tooltip: Create New Person Note
id: new_person
style: primary
actions:
  - type: templaterCreateNote
    templateFile: Templates/People Template.md
    folderPath: People
    fileName: Enter Name
    openNote: true
    openIfAlreadyExists: true
