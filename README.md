# hci-design-portfolio

## What this repository is

This repository holds the complete work of my Week 1 HCI task. It documents the full task from start to finish: setting up a prototyping tool, examining a real website for usability problems, and designing improved screens for it.

The task had three parts:

1. **Set up Figma and explore the design canvas** — create a design file, and practise with frames, shapes and text.
2. **Find usability flaws in an everyday website** — I chose the UAF student portal, used it, and documented its problems with fixes.
3. **Store everything in a design repository** — this GitHub repo, so the wireframes and the evaluation report are kept together in one place.

## What it does

- Records the **Figma practice file** created for the task (linked below).
- Presents a **usability evaluation** of the UAF student portal: 6 real flaws, each explained as *Problem → Why it's bad → Suggested fix*, with screenshot evidence.
- Shows the **redesign**: three wireframes that fix the flaws found in the evaluation — a new login page, a student dashboard, and a results page.

## What it has

```
hci-design-portfolio/
├── README.md
├── report/
│   └── Week-01-HCI-Assignment-Report.md
├── evaluation-reports/
│   ├── usability-flaws-uaf-student-portal.md
│   ├── usability-flaws-uaf-student-portal.pdf
│   └── screenshots/
└── wireframes/
    ├── 01-login-redesigned.svg
    ├── 02-student-dashboard.svg
    └── 03-results-page.svg
```

### `report/`
The written report of the task: the HCI design life cycle, the UX workflow, how Figma was set up, what was explored on the canvas, and a summary of the evaluation findings.

### `evaluation-reports/`
The usability evaluation of the **UAF student portal (LMS — lms.uaf.edu.pk)**, available as Markdown and PDF. The 6 flaws it documents:

1. Login for the whole portal is blocked during result submission, with no date or reason given.
2. The login page mixes two tasks — Login and a separate Result lookup — confusing new students.
3. The password link is labelled "Recover your Account" instead of the standard "Forgot password?".
4. A technical "Cookies must be enabled in your browser" warning is shown to every user.
5. The login page runs on unencrypted HTTP, so passwords are not protected.
6. Getting an account requires a manual request form instead of automatic activation.

The `screenshots/` folder holds the screenshot evidence for these flaws.

### `wireframes/`
Low-fidelity redesign wireframes (SVG files — they can be dragged straight into Figma and edited):

| File | What it shows |
|---|---|
| `01-login-redesigned.svg` | A single-task login page: standard "Forgot password?" link, plain-language notices with dates, HTTPS, and the result lookup moved to its own page. |
| `02-student-dashboard.svg` | The student's home after login: courses, upcoming deadlines, results summary and announcements — everything one click away. |
| `03-results-page.svg` | A dedicated results page: GPA/CGPA summary, subject-wise marks with clear published/pending status, and a PDF download. |

## Figma file

The design file created in Figma for this task: **[HCI-Week-01](https://www.figma.com/design/at8ViHIqW9TE4xJGZvWmHT/HCI-Week-01?node-id=1-4&t=tfFSAsudMghJrwGO-0)** — Page 1 contains a Desktop frame (1440 × 1024), a rectangle, an ellipse and the text "HCI Week 01 — Canvas Exploration". A second page, **"Student Login Design"**, holds a mobile student login design in a mint-green and dark-teal style: a **Login** screen (graduation cap, "Hello! Welcome Student", email and password fields, Forgot Password, Login button, social login options) and a matching **Sign Up** screen (Back to login, email, password and confirm password fields, Sign Up button), each 375 × 812.

## How to view the work

- Read the evaluation online: open `evaluation-reports/usability-flaws-uaf-student-portal.md`.
- Open any wireframe SVG in a browser to view it, or drag it into Figma to edit it.
- Open the Figma link above to see the canvas exploration file.
