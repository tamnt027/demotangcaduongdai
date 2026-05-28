# Overtime Ticket Management — Demo Module

**Cuong Dai Packaging — Internal Demo**

> 🌐 **Live demo:** **https://demotangcaduongdai.onrender.com/**
>
> Open the link in any modern browser (Chrome, Edge, Safari, Firefox) — no installation required.

---

## 1. Purpose

This module digitises the daily process of recording and approving overtime
(OT) for production workers at Cuong Dai Packaging. It replaces paper slips
and ad-hoc spreadsheets with a single web application that gives every role
exactly the view they need:

- **Team Leaders** issue and approve OT tickets for their team.
- **Workers** see their own recorded OT in real time.
- **Management** monitors company-wide OT load with clean statistics.

The result: faster ticket creation, fewer errors, and an instantly auditable
record of every overtime session.

---

## 2. User Roles

The module ships with three distinct roles. Each role sees a tailored
dashboard the moment they sign in.

| Role | Responsibility |
|------|----------------|
| **Manager** | Company-wide oversight: aggregate statistics, per-person breakdowns, full ticket history. |
| **Team Leader** | Creates and approves OT tickets for their production team; can include themselves on a ticket. |
| **Worker** | Reviews their own approved OT by day, week, and month. |

---

## 3. Feature Highlights

### 3.1 Team Leader

- **Create OT ticket** with: date, start time, end time, optional reason,
  and a multi-select list of team members. A single checkbox lets the
  leader add themselves to the ticket.
- **Draft → Approved workflow.** A new ticket starts as a *Draft*. It only
  becomes effective (visible to workers and management) once the leader
  clicks **Approve**.
- **List & filter** their tickets by *Today / This Week / This Month*, with
  a date picker for any specific day.
- **Live statistics panel** for the selected period:
  - Total OT hours
  - Number of unique workers participating
  - Average hours per worker
  - Number of OT sessions
- **Delete** a draft or approved ticket when required.

### 3.2 Worker

- **Daily ledger** of the current month: every day in the month shows
  either the approved OT sessions of that day, or *No overtime*.
- **Monthly summary tiles**:
  - Total OT hours for the month
  - Total number of OT sessions
  - Average hours per session
- **Drill-down**: tapping any session opens the full ticket detail
  (period, duration, team mates, reason, leader who created it).

### 3.3 Manager

- **Period filter** (*Today / This Week / This Month* or pick a date).
- **Four headline statistics** for the selected period:
  - Total OT hours across the company
  - Number of unique workers in OT
  - Average hours per worker
  - Number of OT sessions
- **People ranking table** — every team leader and worker that performed
  overtime in the period, with role, team, times, total hours, and
  average per session, sorted by total hours descending.
- **Ticket grid** — every approved OT ticket in the period, openable for
  full detail.

---

## 4. Built-in Business Rules

The module enforces the rules typically expected of an OT system:

1. **Date must be today or later** — past days cannot be back-filled from
   this screen.
2. **Date must stay in the current month** — leaders cannot schedule OT
   into next month.
3. **End time must be after start time.**
4. **No past time slots** — if the leader picks *today*, the end time
   must still be in the future.
5. **At least one worker required** on every ticket.
6. **Drafts are invisible to workers and management** — workers only see
   tickets the leader has explicitly **Approved**.

---

## 5. Multilingual Interface

Every screen is fully translated into:

- 🇬🇧 **English** (default)
- 🇻🇳 **Vietnamese**
- 🇨🇳 **Chinese (Simplified)**

A flag switcher is pinned at the bottom centre of every page. The user's
language choice is remembered across refreshes, browser restarts, and
logout / login cycles.

---

## 6. Demo Accounts

The shared password for **all** accounts is `demo@123`.

| Username | Role | Name | Team |
|----------|------|------|------|
| `gd`  | Manager     | Liu Xiao Yong       | Management |
| `tt1` | Team Leader | Trần Thanh Bình     | Production Team 1 |
| `tt2` | Team Leader | Lê Minh Quân        | Production Team 2 |
| `cn1` | Worker      | Phạm Văn Hùng       | Production Team 1 |
| `cn2` | Worker      | Vũ Thị Hà           | Production Team 1 |
| `cn3` | Worker      | Đỗ Quốc Tâm         | Production Team 1 |
| `cn4` | Worker      | Bùi Thị Nga         | Production Team 1 |
| `cn5` | Worker      | Hoàng Văn Sơn       | Production Team 2 |
| `cn6` | Worker      | Mai Thị Lan         | Production Team 2 |
| `cn7` | Worker      | Ngô Tiến Đạt        | Production Team 2 |
| `cn8` | Worker      | Trịnh Thị Yến       | Production Team 2 |

The login screen also offers one-click buttons that auto-fill the demo
accounts, so reviewers do not have to type credentials.

---

## 7. Suggested 3-minute Walk-through

A short script for presenting the module to management:

1. **Open** https://demotangcaduongdai.onrender.com/
2. **Sign in as `tt1`** (Team Leader, Production Team 1).
3. Click **+ Create Ticket** → set today's date, 17:30 – 20:00, tick all
   team members → **Create**. Notice the ticket appears as a *Draft*.
4. Click **Approve** on the new draft — it turns green (Approved).
5. Switch the language flag at the bottom to **Vietnamese**, then
   **Chinese**, to demonstrate full localisation.
6. **Sign out** → **Sign in as `cn1`** (Worker, Team 1). The just-approved
   ticket now appears in today's row of the monthly ledger. The monthly
   tiles update automatically.
7. **Sign out** → **Sign in as `gd`** (Manager). The new session is
   reflected in the company totals and in the per-person table.

---

## 8. Technical Notes (for IT)

- **Front-end only**, single-page web application (React, served as a
  static site). No backend or database is required for the demo.
- **Data store**: the browser's `localStorage`. Seed data (accounts,
  tickets for prior days of the current month) is created automatically
  on first visit, so the dashboards are never empty.
- **Hosting**: deployed as a static site on Render.com from the GitHub
  repository, with automatic redeploy on every commit to `main`.
- **Source**:
  [github.com/tamnt027/demotangcaduongdai](https://github.com/tamnt027/demotangcaduongdai)

A production version would add a real backend (REST API + database) for
multi-device data sharing and audit logging, plus integration with the
company HR / payroll system. The current demo proves the user flows and
the UX; the back-end work is a separate engineering task.

---

## 9. Contact

**Demo by Tam Ng** — `0777623579`

For questions, scope changes, or a production-ready estimate, please
reach out directly.

---

*© 2026 Cuong Dai Packaging — Internal Demo*
