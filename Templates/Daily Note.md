<%*
	const created_on = tp.date.now("dddd, DD-MMM-YYYY");
-%>
---
createdOn: <% created_on %>
tags: daily

---
# <% "Daily Note, " + created_on %>

## Daily Updates
- 
## Tasks and Notes

- [ ]  

## Map of Contents
- [[📅Meetings MOC]] - `BUTTON[new_meeting]`
- [[👥People MOC]] - `BUTTON[new_person]`
- [[📘Projects MoC]]

### [[TODO Tracker]]

## The files of the day
```dataview 
LIST
FROM ""
WHERE createdOn = this.createdOn
SORT createdOn DESC
```
---

### Custom Status Reference Sheet
- [?] ?
- [R] R
- [!] !
- [i] i
- [I] I
- [B] B
- [P] P
- [C] C
- [r] r
- [d] d
- [T] T
- [t] t
- [@] @
- [f] f


