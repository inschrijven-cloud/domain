# Domain

("domain" as in "domain knowledge" or "domain driven design", not "domain" as in "domain name")

## Entity types

### Organisation

An organisation organises usually one, but possibly multiple playgrounds.

### Child

A child is a participant of the playground.

### Crew member

A crew member is a someone who organises activities and plays with the children. On most playgrounds, crew members are volunteers.

### Day

A day is a date on which activities can happen. Days are divided in parts, called shifts.

### Shift

A shift is a block of time on a date. It's part of a day. Shifts have a start time, end time and location. They also usually have a cost.

### Presences

#### Child presences

Children can be present on a shift. That means they attended that shift.

#### Crew presences

Crew can be present on a shift. That means they attended that shift.

## Entity identifiers

| Entity type  | Identifier | Example                                | Notes |
|--------------|------------|----------------------------------------|-------|
| Organisation | Canonical name of the organisation | `de-speelberg`  | Only lower case, numbers and `-` (no spaces). |
| Child        | UUID       | `00113398-8e57-40f6-aac2-ca8a4f29a6e9` | Can't use the first and last name combination as identifier, because (1) not unique and (2) they are often misspelled and need to be corrected. |
| Crew         | UUID       | `1c18d33e-2900-4db9-ad66-2486eec8f069` | Same remarks as with children. |
| Shift        | UUID       | `e36260fc-a67f-44f1-ae0f-e748e3020a2d` | Can't use the combination of date and shift kind as identifier, because multiple shifts may be happening concurrently at different locations. |
| Day          | Date in ISO8601 format | `2017-02-27`               | Note the leading zeroes for days and months. |
| Presence (child) | id of the day + `--` + id of the shift + `--` + id of the child | `2017-02-27--e36260fc-a67f-44f1-ae0f-e748e3020a2d--00113398-8e57-40f6-aac2-ca8a4f29a6e9` | |

