# Homework 02 — Asynchronous JavaScript & Promises

**Author:** Olena Solonikova

This project contains the homework assignment for **Topic 4: Asynchronous JavaScript & Promises**. It is built with **Vite** and consists of two independent pages demonstrating asynchronous operations, timers, and promise handling.

## Project Overview

The repository includes:

* **1-timer.html** — Countdown Timer built with **flatpickr** and **iziToast**.
* **2-snackbar.html** — Promise Generator that creates delayed promises and displays notifications using **iziToast**.

---

## Features

* Vite-powered project setup.
* Interactive countdown timer with date and time selection.
* Promise generator with configurable delay and result state.
* Toast notifications for user feedback.
* Integration of **flatpickr** and **iziToast** libraries.

---

## Getting Started

Install project dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

Open your browser and navigate to:

```
http://localhost:5173
```

---

# Task 1 — Countdown Timer

The first page implements a countdown timer that tracks the remaining time until a selected future date.

## Interface

The page contains:

* A date/time input field.
* A **Start** button.
* Countdown elements displaying:

  * Days
  * Hours
  * Minutes
  * Seconds

The timer values are updated through `data-*` attributes.

## Functionality

* The date picker is implemented using **flatpickr**.
* The **Start** button is disabled until the user selects a valid future date.
* Selecting a past date triggers an **iziToast** notification:

```
Please choose a date in the future
```

* When the timer starts:

  * the input field becomes disabled;
  * the Start button becomes inactive;
  * the countdown updates every second.

* Once the countdown reaches zero:

  * the timer stops automatically;
  * the display shows `00:00:00:00`;
  * the input field becomes available again;
  * the Start button remains disabled until another valid date is selected.

Milliseconds are converted into days, hours, minutes, and seconds using the provided `convertMs()` helper.

---

# Task 2 — Promise Generator

The second page demonstrates asynchronous operations with JavaScript Promises.

## Interface

The form contains:

* A numeric input for delay in milliseconds.
* Two radio buttons:

  * **Fulfilled**
  * **Rejected**
* A submit button.

## Functionality

After submission:

* A Promise is created.
* `setTimeout()` delays its execution.
* Depending on the selected option, the Promise either resolves or rejects.

After completion, an **iziToast** notification appears.

Success example:

```
✅ Fulfilled promise in 1500ms
```

Failure example:

```
❌ Rejected promise in 1500ms
```

---

# Code Quality

The project follows several development principles:

* Clean and modular structure.
* Reusable helper functions.
* Consistent formatting with Prettier.
* No console errors or warnings during execution.
* Basic accessibility support for interactive elements.

---

# Deployment

Before deploying to GitHub Pages, configure the build script in `package.json`:

```json
"build": "vite build --base=/goit-advancedjs-hw-02/"
```

Then execute:

```bash
npm run build
```

Push the latest changes to the `main` branch. If GitHub Actions is configured, deployment to `gh-pages` will happen automatically.

---

## Live Demo

https://olena3333.github.io/goit-advancedjs-hw-02/

---

# Quick Test Checklist

### Countdown Timer

* Run `npm run dev`.
* Open `1-timer.html`.
* Verify that the **Start** button is disabled initially.
* Select a future date and start the timer.
* Confirm that the countdown updates every second and stops at zero.

### Promise Generator

* Open `2-snackbar.html`.
* Enter a delay value (for example `1500`).
* Choose either **Fulfilled** or **Rejected**.
* Submit the form and verify that the corresponding notification appears after the specified delay.

