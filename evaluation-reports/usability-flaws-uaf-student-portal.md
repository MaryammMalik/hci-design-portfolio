# Usability Evaluation — UAF Student Portal (LMS)

**Product evaluated:** University of Agriculture Faisalabad (UAF) student portal — the Learning Management System at `lms.uaf.edu.pk`, used by students for courses, assignments and results.
**Date of evaluation:** 16 November 2026
**Method:** Heuristic evaluation — the portal's login page and account process were inspected against Nielsen's 10 usability heuristics. Each flaw is written as **Problem → Why it is bad → Suggested fix**, with a severity rating (1 = minor, 4 = usability catastrophe).
**Evidence:** Every quoted message below was read directly from the live login page on 16 Nov 2026 — the page currently displays the notice *"Student Login Access is blocked till result submission."* Screenshots to attach are listed in `screenshots/README.md` (login page, blocked-access banner, and the browser's "Not secure" indicator for the HTTP address).

---

## Flaw 1 — Students are locked out of the whole portal during result submission, with no date or explanation

- **Problem:** The login page shows a banner: *"Student Login Access is blocked till result submission."* While it is shown, students cannot log in at all — no courses, no assignments, no deadlines. The banner gives **no date** when access will return and **no reason**.
- **Why it is bad:** It violates *visibility of system status* and *help users recognise, diagnose and recover from errors*. Students cannot tell whether the problem is the portal, their account, or their password, so they keep retrying, reset passwords unnecessarily, or assume their account is broken. Blocking the *entire* LMS because of one administrative task (result submission) punishes every student for something unrelated to them.
- **Suggested fix:** Never block the whole portal for one back-office task — restrict only the results module. If a block is unavoidable, the banner must say **from when, until when, and why** ("Login is paused for result entry until Friday 20 Nov, 5 pm. Your courses and assignments are safe."), and students should still get read-only access to their course materials.
- **Severity:** 4 (catastrophe) · **Heuristic:** Visibility of system status

## Flaw 2 — Two different tasks are mixed on one login page: "Login" and "Result"

- **Problem:** The same page contains the normal login (Username + Password) **and** a separate "Result" box asking for a Registration No. A new student cannot tell which one they are supposed to use, and the two boxes look equally important.
- **Why it is bad:** It violates *match between the system and the real world* and *recognition rather than recall*. Students regularly type their registration number into the username field (or the reverse), get an error, and conclude their account does not work. Every extra decision on a login page slows down the one task the page exists for.
- **Suggested fix:** One page, one task. Keep only Username + Password on the login page, and move "Check result by Registration No" to its own clearly labelled page, linked as a separate button *below* the login box: "Not a student yet? Check your entry-test result →".
- **Severity:** 3 (major) · **Heuristic:** Match between system and the real world

## Flaw 3 — "Recover your Account" instead of "Forgot password?"

- **Problem:** The password-help link is labelled **"Recover your Account"** and sits away from the password field. The actual UAF password-retrieve process is on yet another page and asks for a CNIC number (without dashes) plus a captcha.
- **Why it is bad:** It violates *consistency and standards*. Every major platform (Google, Facebook, banking apps) uses "Forgot password?" directly under the password field, so that is where students look. A non-standard label in a non-standard place means students cannot find it when they are locked out — exactly when they are most stressed — and the CNIC-plus-captcha process adds recall burden (students must remember the exact CNIC format) at the worst moment.
- **Suggested fix:** Put a standard **"Forgot password?"** link immediately under the password field. The reset flow should accept the registration number *or* CNIC (any format — the system can strip dashes itself) and send a reset link to the registered email/phone, in one step.
- **Severity:** 3 (major) · **Heuristic:** Consistency and standards

## Flaw 4 — Technical warning "Cookies must be enabled in your browser" shown to every user

- **Problem:** A warning about browser cookies is displayed prominently at the top of the login page to all visitors, in technical language.
- **Why it is bad:** It violates *match between the system and the real world* (speak the user's language). Most students do not know what a cookie is; the message reads like an error, so many assume the portal is broken or that they did something wrong. A warning that does not apply to almost anyone should not be the first thing everyone sees.
- **Suggested fix:** Remove the permanent warning. Detect the problem only if it actually happens, and then explain it in plain words with the solution: "Your browser is blocking the login. Tap ⋮ → Settings → Allow cookies for this site, then try again."
- **Severity:** 2 (minor, but affects trust) · **Heuristic:** Match between system and the real world

## Flaw 5 — The login page is served over plain HTTP ("Not secure")

- **Problem:** The portal address is `http://lms.uaf.edu.pk` — the login page where students type their password is **not encrypted**, and browsers flag it as "Not secure".
- **Why it is bad:** It violates *error prevention* and basic user trust. On shared networks (hostel Wi-Fi, net cafés — which UAF's own admission guidelines mention students using), an unencrypted password can be intercepted. It also trains students to ignore browser security warnings, which makes them vulnerable everywhere else.
- **Suggested fix:** Serve the whole LMS over HTTPS with an automatic redirect from HTTP, at no cost via a free certificate (e.g. Let's Encrypt). No login page should ever be HTTP.
- **Severity:** 4 (catastrophe — security) · **Heuristic:** Error prevention

## Flaw 6 — Getting an account is a manual, multi-step process ("Register / Activate Your Account")

- **Problem:** A new student cannot simply sign up. Per the university's own LMS guide, the student must first **submit an LMS request form** to get credentials, then use "Register / Activate Your Account" on the login page. The university's admission guidelines even warn students not to ask a net café or friends to register for them — evidence that the process is hard enough that students hand their personal data to strangers.
- **Why it is bad:** It violates *flexibility and efficiency of use* and *error prevention*. Every extra step and waiting period loses students; the ones who struggle most (first-generation students, students from villages with no computer at home) are pushed toward exactly the unsafe workaround the university warns against.
- **Suggested fix:** Create accounts automatically from the admission record — the university already has every student's registration number, CNIC and phone number. The student enters their registration number, receives an OTP on their registered mobile, sets a password, and is logged in: one sitting, under two minutes, no forms and no third parties.
- **Severity:** 3 (major) · **Heuristic:** Flexibility and efficiency of use

---

## Summary table

| # | Flaw | Heuristic | Severity |
|---|---|---|---|
| 1 | Whole-portal login block, no date or reason | Visibility of system status | 4 |
| 2 | Login and Result lookup mixed on one page | Match with the real world | 3 |
| 3 | "Recover your Account" instead of "Forgot password?" | Consistency and standards | 3 |
| 4 | "Cookies must be enabled" jargon warning for everyone | Match with the real world | 2 |
| 5 | Login over unencrypted HTTP | Error prevention | 4 |
| 6 | Manual request-form process to get an account | Flexibility and efficiency | 3 |

**Overall judgement:** the portal works for students who already know its habits, but it fails new and stressed users at the exact moments they need it most — first login, forgotten password, and result season. The redesign wireframes in the `wireframes/` folder address flaws 1–3 and 6 directly: a single-task login page, a standard "Forgot password?" link, plain-language notices with dates, and a dashboard that puts courses, deadlines and results one click away.
