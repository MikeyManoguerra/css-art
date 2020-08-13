ppp 4-27


BUGS:

Frontend:
- write tests for atom components
- "[mobx.array Attempt to read an array index (0) that is out of bounds (0). Please check length first. Out of bound indices will not be tracked by MobX"
- fix test errors
- -authstore login functions sets username to undefined
- mobile!
- a 404 page, and  a redirect in the nested router to it
- insurance name should influence 'has insurance'
- tabbing through column headers seems like there are two things (a button to toggle order, and something else that is focusable)
- queue tabs go over nav on scroll
- if someone is already in the queue, dont re -add them
- paginate the participants in the front end somehow
- styling on the inputs for disabled/error (display name in heading?) https://material-ui.com/customization/components/
- current participant id in route?

Backend:

- if someone is already in the queue, dont re -add them

-  better loading messages for queue and participant table
- last  four ssn not gonna work


- notes dialogue on queue broken
- responsiveness on table columns
- storing participant names on the front end?
- participant table needs margin bottom
- a route that gets all the visits for a participant
- seperate store for existingParticipant page?
- MAKE SURE particpant and visit data align!
- sanitize search queries

- establish permanent front end state:
- insurers
- programs
- When you edit a participant, that should fetch data from store in that moment, not have it stored in the row data
- get service name by getting service from queue[i].service.id === visit.service (use the store)

"Quick Entry" view.
on participant table, a live search text box, and a dropdown for available quick entry forms.
- pick the quick program ( dropdown triggers API call to Form table to get the questions)
- filter the participants
- select participant
- enter data
- submission creates a visit w/o FDE, then uses the visit_id to create the program_data entry

How to get the data:

visit_id > program_id > formTable.filter(program_id) for_each form_data table,  form_data.get(visit_id)





Ticket: 
title: Route on success flag needs to be reset :(route to queue)
body: once route to queue is set to true,  it is never reset. perhaps a larger refactor involved with with error and loading state




OTHER:
a way to get to participant list not thru search.
enforce uniqueness on participants?


METABASE
tester@thebznz.edu
pw: Kf6kFsNKO_q8hT
http://45.55.62.203:3001

https://docs.google.com/spreadsheets/d/1fRHeBHGBo02HcTtpkf4k6YtuLP0iJADYhjAJ4Mf2yeM/edit?usp=sharing

stillAuthenticated in App.js
participant search decide on error handling
validate ppid

readOnly for ppID

Ticket:
Queue should have oldest visit above younger visits for visits of same urgency
- schema(put it off) may change how to filter services on FE, but otherwise api will stay the same 

Ticket : 
	permissions org
	cascading permissions vs restrictive permissions
	i am an administrator, i have permissions of front desk + provider +admin
	or i am front desk, i have front desk permissions but not admin permissions


Ticket: queueStore
line 25
 program.participants = [...data].sort(
this participants is visits


Typography:
- (kicker)

fullWidth queue dropdowns


Dynamic Based upon current action:
- new visit
- past visits
- single visit service list
- single visit service form
(needs a header to say what's going on)
we can use the router to do this. then can auth redirect if the user doesnt have permission



