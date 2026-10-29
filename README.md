# ReSchool

A proof-of-concept web app that moves donated school supplies to the students who need them.

**Live demo:** https://vmedbery.github.io/ReSchool/

## The problem

Some students start the year with more supplies than they need, and others go without. Schools have no simple way to collect extra supplies and get them to the right students.

## How it works

- **Anyone can donate** supplies to any school. A donation starts as a *pledge* and only counts toward the school's stock once the school office *receives* it.
- **Students request** supplies from the school where their student ID is active. A request only takes items out of stock once a school admin *approves* it.
- **Receiving and approving can be partial**: for example, 4 of 10 glue sticks arrive, or 2 of 3 notebooks are approved.
- **Out-of-stock items can still be requested.** Students wait in line, first come first served, and the item shows as **High priority** to donors (see Priority flags below).
- **School admins** choose which items can be donated or requested, set the most allowed per request (and optionally per donation), and manage their student ID roster (active or inactive).
- **Students sign up** with their first and last name, plus a student ID and school if they have one. To use an ID that's on the school's roster, the name and date of birth must match the roster. An ID on a different school's roster is refused, and an ID on no roster is sent to the school admin for approval.
- **Students can cancel** anything not yet approved, but can't edit a request, so no one can jump the line.
- **Optional contact details**: donors can add a business name, phone, email and address; students can add a phone, email and address.
- **My account**: students and donors update their own contact details. Students who signed up without an ID can add one later, as long as the name on the account and their date of birth match the school's roster and no other account at that school uses the ID.
- **Donors** can sign up without any connection to a school and donate to any school.
- **Schools have their own look**: an uploaded icon plus primary and secondary colors.
- **A ReSchool admin** manages schools, supply items, users and rosters across all schools, resets the demo, and exports the setup.

## Priority flags

Donors see two kinds of flags, so they know what each school needs most.

- **Priority** is set by the school. In **Supplies**, a school admin can turn on "Flag as a priority for donors" for any item. It stays on until they turn it off. Items aren't flagged unless the school picks them.
- **High priority** is set by the app. It appears on its own whenever students are waiting for more of an item than the school has on hand, and shows how many units the school is short. It replaces the Priority flag while the shortage lasts, and goes away once donations cover it. If the item was also flagged as Priority, that flag shows again afterward.

Both flags only appear on items the school accepts as donations. High priority items are listed first, with the biggest shortages at the top. The flags show on the donation form, on each school's **Most needed** list, and on the donor's **Schools that need help** list.

## The rules

1. Pledging and requesting never change inventory.
2. Anyone can donate to any school. Donations have no limit unless the school sets one for an item.
3. Students request only from the school where their ID is active, within per-request limits. Out-of-stock items wait in line.
4. Receiving adds to inventory and can be partial.
5. Approving takes from inventory, can be partial, and goes in order of who asked first. 
6. Students sign up with their name. A student ID on the roster only matches with the right name and date of birth; IDs not on any roster need school approval.
7. Students can cancel what hasn't been approved, but never edit a request.

## Demo accounts

This is a proof-of concept and there are no passwords for simplicity. Pick an account on the sign-in screen to impersonate the selected user. 

| Account | Role |
|---|---|
| Jane Doe, John Smith | Students at Houston Adventist Academy |
| Sarah Miller | Student at Demo Adventist School #2 |
| Mary Johnson | Signed up with a name only. Can donate now, and can add a student ID from **My account** to request supplies |
| Robert Davis | ID waiting for Houston Adventist's approval |
| Pat Rivera | Community donor, Rivera Family Hardware |
| Mr. Castillo / Ms. Oak | School admins for Houston Adventist / Demo School #2 |
| Tabitha | ReSchool admin (configuration & demo reset) |

To try a matched sign-up: **Emily Jones**, student ID **100103** at Houston Adventist Academy, born **June 21, 2011**.

## Resetting the demo

Both options are at the bottom of the page when signed in as the ReSchool admin.

- **Reset demo data** clears every request and donation and puts stock back to its starting counts. Schools, supplies, settings, rosters and users stay as they are. Use this before a presentation.
- **Restore original setup** puts *everything* back to the built-in setup, including schools, users and rosters. It asks for a second tap first. Use this if the setup gets changed beyond repair, or to load a new default setup on a browser that already has saved data.

## Limitations (it's a proof of concept)

- Data is saved in each person's browser, so different devices don't share data.
- There are no real passwords or security. Matching name and date of birth makes it harder, not impossible, to sign up as someone else.
- A real version would need a shared database and real sign-in.

