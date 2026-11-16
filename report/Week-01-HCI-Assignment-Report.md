# Week 1 Assignment — Introduction to HCI & User Experience Workflow

**Course:** Human Computer Interaction (HCI)
**Week:** 1 — Introduction to HCI & User Experience Workflow
**Student:** Maryam Malik

---

## Objectives

1. Understand the HCI design life cycle and set up the prototyping environment.
2. Identify usability flaws in an existing everyday website/app.
3. Create an initial design repository on GitHub to store design wireframes and evaluation reports.

---

## 1. The HCI Design Life Cycle

Human Computer Interaction is the study of how people interact with computers, and of how to design computer systems that people can use easily, effectively and with satisfaction. A good interface is not produced in one step — it follows a **life cycle** in which a design is repeatedly built, tested with users, and improved. This is called **user-centred design (UCD)**: the user, not the technology, stays at the centre of every stage.

| Stage | What happens | Output |
|---|---|---|
| **1. Understand / Research** | Study the users, their tasks, goals and context — interviews, questionnaires, observation, and analysis of existing systems. | User requirements, personas, task descriptions |
| **2. Design** | Turn requirements into ideas: sketches, storyboards, navigation structure, low-fidelity wireframes. Several alternatives are explored before choosing one. | Sketches, wireframes, design concepts |
| **3. Prototype** | Build a working model — first low-fidelity (paper-style), later high-fidelity in a tool like Figma, with realistic content and interactions. | Clickable prototype |
| **4. Evaluate** | Test the prototype with real users, or with expert methods such as heuristic evaluation and cognitive walkthrough. Measure errors, time on task and satisfaction. | Evaluation report, list of usability problems |
| **5. Implement & Refine** | Fix the problems found, implement the design, and evaluate again. The loop repeats until the usability goals are met. | Improved, usable product |

The life cycle is **iterative**: evaluation is not the last step, it feeds back into design. A flaw found on a cheap wireframe costs almost nothing to fix; the same flaw found after development is expensive. That is why Week 1 already includes an evaluation of an existing product (Section 3) before any new design work.

Two rules guide every stage:

- **Know the user** — design for the user's tasks, vocabulary and mental model, not the developer's.
- **Involve the user early and often** — small, frequent tests beat one big test at the end.

---

## 2. UX Workflow and the Prototyping Environment (Figma)

### 2.1 The UX workflow

The user experience (UX) workflow is the practical path a design takes from an idea to a tested interface:

**Discover → Define → Develop → Deliver**

- **Discover** — research users and the problem (this week's evaluation of the UAF portal belongs here).
- **Define** — agree the exact problem and requirements.
- **Develop** — sketch, wireframe and prototype possible solutions.
- **Deliver** — test, refine and hand over the final design.

### 2.2 Tool selected: Figma

The prototyping environment for this course is **Figma** (free Starter plan):

- Runs in the browser — nothing to install, works on any laptop.
- The industry-standard tool for wireframing and prototyping.
- Files are shared by a link, so a teacher or teammate always sees the latest version.
- A dedicated **Prototype mode** links screens into a clickable flow, needed in later weeks.

*(Alternative considered: Balsamiq — very fast for low-fidelity wireframes, but the free trial is limited and it cannot grow into high-fidelity prototypes, so Figma covers more of the course.)*

### 2.3 Setup (about 10 minutes)

1. Go to [figma.com](https://www.figma.com) → **Sign up** (free) with an email address.
2. Create a new **Design file** and name it `HCI-Week-01`.
3. Explore the canvas: draw a frame, a rectangle and text, and move things around.

**Figma file created for this assignment:** [HCI-Week-01](https://www.figma.com/design/at8ViHIqW9TE4xJGZvWmHT/HCI-Week-01?node-id=1-4&t=tfFSAsudMghJrwGO-0) — it contains a Desktop frame (1440 × 1024), a rectangle, an ellipse and the text "HCI Week 01 — Canvas Exploration", arranged on the canvas during the exploration.

### 2.4 What was explored on the Figma canvas

| Area of Figma | What it does | What I tried |
|---|---|---|
| **Canvas & Frames** | The canvas is the infinite workspace; a Frame is one screen (phone/tablet/desktop presets). | Added a Desktop frame (1440 × 1024) and a Mobile frame (390 × 844). |
| **Shape & Text tools** | Rectangles, ellipses, lines and text — the building blocks of a wireframe. | Drew the boxes and labels that became the wireframes in the `wireframes/` folder. |
| **Layers panel** | Lists every element in order; grouping keeps a screen organised. | Grouped a header (logo + navigation) into one group. |
| **Components** | Reusable elements (e.g. a button) that update everywhere when edited once. | Turned a button into a component and reused it on two screens. |
| **Auto Layout** | Makes groups resize intelligently, like real CSS flexbox. | Applied Auto Layout to a navigation bar so items stay evenly spaced. |
| **Prototype mode** | Links frames with clickable connections to simulate navigation. | Linked the login button to the dashboard screen and previewed the flow. |
| **Share / Version history** | Anyone with the link can view or comment; every change is versioned. | Set the file to "anyone with the link can view". |

The three wireframes produced from this exploration are stored as SVG files in the `wireframes/` folder — an SVG can be dragged straight into Figma and edited there.

---

## 3. Usability Flaws in an Existing App — Summary

The full report is in **`evaluation-reports/usability-flaws-uaf-student-portal.md`** (with screenshots). In brief:

- **Product:** the UAF student portal (LMS, `lms.uaf.edu.pk`) — an everyday system every student uses for courses, assignments and results.
- **Method:** heuristic evaluation against Nielsen's 10 heuristics; each flaw written as *Problem → Why it is bad → Suggested fix*, with a severity rating.
- **The six flaws found:**
  1. The whole portal's login is blocked during result submission, with no date or reason (severity 4).
  2. Login and a separate "Result" lookup are mixed on one page, confusing new students (severity 3).
  3. The password link is labelled "Recover your Account" instead of the standard "Forgot password?" (severity 3).
  4. A technical "Cookies must be enabled in your browser" warning is shown to every user (severity 2).
  5. The login page runs over unencrypted HTTP — passwords are not protected (severity 4).
  6. Getting an account needs a manual request form instead of automatic activation (severity 3).
- **Redesign response:** the three wireframes in `wireframes/` — a single-task login page with a standard "Forgot password?" link and dated, plain-language notices; a dashboard with courses, deadlines and results one click away; and a dedicated results page that always shows status.

---

## 4. GitHub Design Repository

An initial design repository has been created on GitHub to store all design artefacts for this course:

- **Repository name:** `hci-design-portfolio`
- **Structure:**

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

Each coming week will add its wireframes and evaluation reports to the same folders, so the repository becomes the complete design record (portfolio) for the course.

---

## 5. Conclusion

Week 1 established the three foundations of the course: (1) design is an **iterative, user-centred life cycle**, not a single step; (2) the **prototyping environment (Figma)** is set up and its canvas, frames, components and prototype mode have been explored; and (3) a first **heuristic evaluation** of a real, everyday system — the UAF student portal — shows how quickly serious usability flaws can be found with Nielsen's heuristics, and how each flaw leads directly to a concrete design fix in the wireframes. The GitHub repository `hci-design-portfolio` is ready to hold all of this work.
