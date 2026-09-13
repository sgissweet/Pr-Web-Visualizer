# Polynomial Regression — Step-by-Step Visualizer

A single-page web application that explains how **Polynomial Regression** works, step by step, with a strong focus on making the underlying math approachable for beginners. The entire app — HTML, CSS, and JavaScript — lives in one self-contained file, [`index.html`](./index.html), so it can be deployed directly on **GitHub Pages** with no build step.

All page content is written in English.

## Specification

### Format
- Single HTML file only (embedded HTML, CSS, and JavaScript — no external build tooling).
- Must be deployable as a static site on GitHub Pages.
- All content on the page is in English.

### Theme
- Black background with a professional, polished visual style.

### Header
- Short text explaining the topic and the core principle of Polynomial Regression.

### Footer
- Compact, appropriately sized.
- Lists the group members and "CE KMITL".

### Body Layout
The body is split into two floating columns (left / right), each with its own **independent vertical scrollbar**.

**Left column**
- **Top — Data Canvas / Input:** an area for managing data points. Supports both randomly generating data and letting the user click to create or delete points manually.
- **Bottom — Hyperparameters & Controls:** a panel for tuning the algorithm's hyperparameters, with control buttons for **Step-by-step Execution** and **Play until Convergence**.

**Right column**
- **Top — Model State / Structure:** shows the model's internal state changing step by step, in an easy-to-follow way (e.g., matrices, data structures, the weight vector).
- **Bottom — Loss Graph:** a chart showing the loss value decreasing over each step/epoch.

### Interaction
Whenever the model updates (on Step or on Convergence), the Data Canvas on the left must clearly reflect the change — for example, by redrawing the decision boundary / fitted curve, or updating point colors.

## Current Implementation

`index.html` already implements the full spec above:

| Requirement | Where it lives in `index.html` |
|---|---|
| Black, professional theme | CSS custom properties in `:root` (`--bg`, `--panel`, gradient background) |
| Header with topic + principle | `<header>` block introducing Polynomial Regression and Gradient Descent |
| Footer with members + CE KMITL | `<footer>` block (placeholder member names — update before submission) |
| Floating two-column layout with independent scrollbars | `main` grid (`.col`) + `.panel-body` with custom `::-webkit-scrollbar` styling |
| Data Canvas: random + click add/remove | `#dataCanvas`, `randomizeData()`, `addOrRemovePoint()` |
| Hyperparameters & Controls | Degree, learning rate, epochs/tick, convergence ε, max epochs sliders; `btnStep`, `btnPlay`, `btnReset` |
| Model State / Structure | Equation box, weight vector table, standardized feature matrix preview, gradient descent update-rule formulas |
| Loss Graph | `#lossCanvas` rendered by `renderLossGraph()`, updated every epoch |
| Canvas updates on Step/Play | `renderDataCanvas()` redraws the fitted polynomial curve after every `trainEpoch()` call |

## Deployment (GitHub Pages)

1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to "Deploy from a branch".
4. Select the `main` branch and the `/ (root)` folder, then save.
5. GitHub Pages will serve `index.html` directly — no build step required.

## Group Members

- Member 1
- Member 2
- Member 3
- Member 4

**CE KMITL** — Department of Computer Engineering

*(Replace the placeholder names above with the actual group members before submission.)*
