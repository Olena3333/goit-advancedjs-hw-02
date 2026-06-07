Homework 02 — Asynchronous JavaScript & Promises This repository contains the
homework for Topic 4: Asynchronous JavaScript and Promises. The project is built
with Vite and includes two exercises implemented as separate pages:

1-timer.html — Countdown Timer (uses flatpickr and iziToast) 2-snackbar.html —
Promise generator + notifications (uses iziToast) This README summarizes the
tasks, acceptance criteria, and how to run the project locally.

Checklist (what this repo implements) A Vite-based project scaffold. A countdown
timer with date/time picker and formatted display. A promise generator that
resolves or rejects after a delay and shows toast notifications. Uses flatpickr
for date selection and iziToast for user messages. Setup Install dependencies:
npm install Start the development server: npm run dev Open the app in your
browser: http://localhost:5173

Task 1 — Countdown Timer (1-timer.html) Goal: implement a countdown timer that
counts down to a user-selected date and time.

Key UI elements (to be present in 1-timer.html):

An input: <input type="text" id="datetime-picker" /> for date/time. A start
button: <button type="button" data-start>Start</button> (disabled until a valid
future date is selected). Timer fields showing days, hours, minutes, seconds
using data-\* attributes (data-days, data-hours, data-minutes, data-seconds).
Requirements and behavior:

Use flatpickr to select date/time. Import both the library and its CSS. When the
picker closes, validate the selected date: If it's in the past, show a message
(use iziToast) saying "Please choose a date in the future" and keep the Start
button disabled. If it's in the future, enable the Start button. Clicking Start
begins the countdown (updates every second) and disables the input and Start
button to prevent changing the date while running. The timer displays remaining
time as days:hours:minutes:seconds. Days may have more than two digits;
hours/minutes/seconds must be two-digit with a leading zero when needed (use
padStart or an addLeadingZero helper). When remaining time reaches zero the
timer stops, the display shows 00:00:00:00, the input becomes enabled again, and
Start remains disabled. Use the provided convertMs(ms) function to compute
days/hours/minutes/seconds from milliseconds. Acceptance criteria (what the
mentor will check):

flatpickr and iziToast are integrated (including their CSS imports). Start
button is disabled on initial load and until a valid future date is selected.
Choosing a past date shows the "Please choose a date in the future" notification
and keeps Start disabled. Choosing a future date enables Start. Clicking Start
disables input and Start, starts the countdown, updates the display every
second, and stops at 00:00:00:00. Helpful hints:

Import flatpickr and its CSS: import flatpickr from 'flatpickr'; import
'flatpickr/dist/flatpickr.min.css'; Import iziToast and its CSS: import iziToast
from 'izitoast'; import 'izitoast/dist/css/iziToast.min.css'; Task 2 — Promise
Generator (2-snackbar.html) Goal: build a small UI that creates promises that
either resolve or reject after a user-specified delay and shows notifications
for each outcome.

Key UI elements (to be present in 2-snackbar.html):

A form with a numeric input for delay in milliseconds:
<input type="number" name="delay" required />. Two radio buttons for the desired
result: fulfilled or rejected. A submit button to create the notification.
Behavior and requirements:

On form submit, create a promise that either resolves or rejects after the
specified delay (use setTimeout). The promise's resolved/rejected value should
be the delay in milliseconds. Handle the promise outcome and show a toast
notification using iziToast: On success: show a message like ✅ Fulfilled
promise in ${delay}ms. On failure: show a message like ❌ Rejected promise in
${delay}ms. Acceptance criteria:

iziToast is integrated (including CSS import). Submitting the form with a delay
and chosen state triggers a notification with the correct text and timing. Notes
about coding and quality Keep code readable and modular. Use small helper
functions (for example, convertMs, addLeadingZero, and a helper to create the
delayed promise). Format code with Prettier and ensure the console shows no
errors or warnings when the page loads. Add basic keyboard accessibility where
it makes sense (focus states, keyboard activation for the Start button, etc.).
Deployment Before building for GitHub Pages, set the --base option in
package.json's build script to --base=/<REPO>/ where <REPO> is your repository
name:

"build": "vite build --base=/<REPO>/", Then run:

npm run build Push to main and the GitHub Actions workflow (if configured)
should deploy the gh-pages branch automatically.

Live demo: https://innaivboiko.github.io/goit-advancedjs-hw-02/

Quick manual check (smoke test) Start dev server: npm run dev. Open 1-timer.html
and verify the Start button is disabled until you choose a future date. Choose a
future date and click Start — confirm the countdown updates each second and
stops at zero. Open 2-snackbar.html, enter a delay (e.g. 1500), choose Fulfilled
or Rejected, and submit — confirm the appropriate toast appears after the
specified delay. If you want, I can also add a short README section showing
where to find the task-related JS modules and small usage examples for the two
pages.
