# ReSchool

A proof-of-concept web app that moves donated school supplies to the students who need them.

**Live demo:** https://vmedbery.github.io/ReSchool/

## The problem

Some students start the year with more supplies than they need, and others go without. Schools have no simple way to collect extra supplies and get them to the right students.

## How it works

- **Anyone can donate** supplies to any school. A donation starts as a *pledge* and only counts toward the school's stock once the school office *receives* it.
- **Students request** supplies from the school where their student ID is active. A request only takes items out of stock once a school admin *approves* it.
- **Receiving and approving can be partial**: for example, 4 of 10 glue sticks arrive, or 2 of 3 notebooks are approved.
- **Out-of-stock items can still be requested.** Students wait in line, first come first served, and the item shows as **High priority** to donors.
- **School admins** choose which items can be donated or requested, set the most allowed per request (and optionally per donation), and manage their student ID roster (active or inactive).
- **Students sign up** with their first and last name, plus a student ID and school if they have one. To use an ID that's on the school's roster, the name and date of birth must match the roster. An ID on a different school's roster is refused, and an ID on no roster is sent to the school admin for approval.
- **Students can cancel** anything not yet approved, but can't edit a request, so no one can jump the line.
- **Optional contact details**: donors can add a business name, phone and email; students can add a phone and email.
- **Donors** can sign up without any connection to a school and donate to any school.
- **Schools have their own look**: an uploaded icon plus primary and secondary colors.
- **A ReSchool admin** manages schools, supply items, users and rosters across all schools, resets the demo, and exports the setup.

## The rules

All business rules live in one section of `index.html`, marked **CORE RULES**:

1. Pledging and requesting never change inventory.
2. Anyone can donate to any school. Donations have no limit unless the school sets one for an item.
3. Students request only from the school where their ID is active, within per-request limits. Out-of-stock items wait in line.
4. Receiving adds to inventory and can be partial.
5. Approving takes from inventory, can be partial, and goes in order of who asked first.
6. Students sign up with their name. A student ID on the roster only matches with the right name and date of birth; IDs not on any roster need school approval.
7. Students can cancel what hasn't been approved, but never edit a request.

## Demo accounts

There are no passwords. Pick an account on the sign-in screen.

| Account | Role |
|---|---|
| Jane Doe, John Smith | Students at Houston Adventist Academy |
| Sarah Miller | Student at Demo Adventist School #2 |
| Mary Johnson | Signed up with a name only (can donate, not request) |
| Robert Davis | ID waiting for Houston Adventist's approval |
| Pat Rivera | Community donor, Rivera Family Hardware |
| Mr. Castillo / Ms. Oak | School admins for Houston Adventist / Demo School #2 |
| Tabitha | ReSchool admin (reset, export settings) |

To try a matched sign-up: **Emily Jones**, student ID **100103** at Houston Adventist Academy, born **June 21, 2011**.

## Limitations (it's a proof of concept)

- Data is saved in each person's browser, so different devices don't share data.
- There are no real passwords or security. Matching name and date of birth makes it harder, not impossible, to sign up as someone else.
- A real version would need a shared database and real sign-in.

## Changing the default setup

Changes made inside the app are saved only in that browser. To make a setup the starting point for everyone:

1. Sign in as the ReSchool admin and choose **Export default settings**.
2. Copy the text.
3. Paste it into `DEFAULT_SETUP` near the top of the script in `index.html` (or hand it to Claude to do).

## Running it

It's a single file. Open `index.html` in any browser, or host it on any static host such as GitHub Pages.
