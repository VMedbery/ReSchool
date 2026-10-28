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
- **Students sign up** with a student ID and school, or with their name. An ID that isn't on the school's roster is sent to the school admin for approval.
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
6. Students sign up with a name, or a student ID. IDs not on the roster need school approval.

## Demo accounts

There are no passwords. Pick an account on the sign-in screen.

| Account | Role |
|---|---|
| Jane Doe, John Smith | Students at Houston Adventist Academy |
| Sarah Miller | Student at Demo Adventist School #2 |
| Mary Johnson | Signed up with a name only (can donate, not request) |
| Robert Davis | ID waiting for Houston Adventist's approval |
| Pat Rivera | Community donor (no school connection) |
| Mr. Castillo / Ms. Oak | School admins for Houston Adventist / Demo School #2 |
| Tabitha | ReSchool admin (reset, export settings) |

## Limitations (it's a proof of concept)

- Data is saved in each person's browser, so different devices don't share data.
- There are no real passwords or security.
- A real version would need a shared database and real sign-in.

## Changing the default setup

Changes made inside the app are saved only in that browser. To make a setup the starting point for everyone:

1. Sign in as the ReSchool admin and choose **Export default settings**.
2. Copy the text.
3. Paste it into `DEFAULT_SETUP` near the top of the script in `index.html` (or hand it to Claude to do).

## Running it

It's a single file. Open `index.html` in any browser, or host it on any static host such as GitHub Pages.
