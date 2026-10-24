# CareQueue — Hospital Patient Queue Manager

A responsive Hacktoberfest prototype made with **HTML, CSS and vanilla JavaScript**. No build process, package installation or database is required.

## Run

Open `dist/index.html` in a modern browser. For reliable storage and same-browser multi-tab updates, serve the project using VS Code Live Server, or run `python -m http.server 8080 --directory dist` from this folder and visit http://localhost:8080.

The hosted version is also available through the accompanying CareQueue link. It starts with fictional demo records on its first visit. No external service receives patient records from this application.

## Demonstrate

1. Register a fictional patient and select Consultation, Laboratory or Pharmacy.
2. Review the generated ticket; optionally print it.
3. Complete the department's current sample visit, then select **Call next**.
4. Use the queue filters and name/ticket search to locate records.
5. Transfer an active patient to another department. The old visit completes, and a new ticket joins that department's queue.
6. Open the waiting-room display in another tab on the same browser and origin. Only tickets and departments are shown there.
7. Export the full day's register as a CSV file, or reset the demo to explore again.

## Files

- `dist/index.html`: page layout and accessible registration/ticket dialogs.
- `dist/styles.css`: responsive layout, display screen and print styles.
- `dist/app.js`: queues, patient states, browser storage, filtering, export and printing.

## Queue rules

- Each department has one active patient at a time.
- Routine patients are called in arrival order. Clinical staff handle urgent cases outside this demonstration.
- Queue numbers use department-specific sequences: CON, LAB and PHA.
- Every registration or transfer adds one visit record. The registration total counts visits, not unique individuals.
- Records and counters reset when a new calendar day begins in Africa/Lagos (WAT). Export the register before the day ends if needed. This demo does not archive past days.
- “Time” shows time waiting, time in service, or the completion/cancellation time as appropriate.

## Prototype boundaries

Use fictional patient data only. This is a browser-local demonstration with no staff authentication or backend. It does not synchronize across devices or different browsers, and browser storage is not protected clinical storage. The staff workspace is a demo interface, not a secure role boundary. Multiple tabs on the same browser update via storage events; simultaneous writes are not guaranteed to be transactional. A production deployment needs authenticated staff roles, a protected server database, audit history, concurrency controls, backups and an appropriate clinical/privacy review.

The public display omits names, but staff views, printed tickets and exported CSVs contain the fictional name entered. CSV cells are escaped, including spreadsheet formula prefixes. Text entered in forms is escaped before rendering.

Fonts use optional Google Fonts; system fonts work offline. The application requires a modern browser with dialog, localStorage and Web Crypto support.
