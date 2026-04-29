# StudySync (Capstone Demo)

Students struggle to manage study time effectively across multiple courses. StudySync turns assignments into actionable study tasks and generates an adaptive **Today Plan** based on how many minutes you have available.

## Problem & Motivation
- **Inefficient time management:** hard to allocate time across classes.
- **Syllabus overload:** hard to convert info into tasks.
- **Procrastination & imbalance:** students avoid difficult work or over-focus one class.
- **Lack of adaptive tools:** plans don’t update when time or progress changes.

## System Overview / Architecture
- **UI:** Next.js (App Router) + Tailwind
- **Backend:** Next.js Route Handlers (REST-style API)
- **Database:** SQLite via Prisma ORM
- **Scheduling logic:** server-side plan generator (urgency + difficulty + balance)

Data flow (demo path): UI 􏰒 API 􏰒 DB 􏰒 UI refresh.

## Features Implemented (Demoable)
- Create and list **Courses**
- Create **Assignments** (due date, estimated minutes, difficulty)
- Auto-generate **Study Tasks** in **30-minute chunks**
- **Today Plan**: enter available minutes for today 􏰒 get prioritized tasks
- Mark tasks **Done** and see the plan adapt
- Seeded demo data (5 courses)

## Quickstart

### 1) Install
```bash
npm install
```

### 2) Database setup
```bash
npx prisma migrate dev
npx prisma db seed
```

### 3) Run
```bash
npm run dev
```
Open http://localhost:3000

## Demo Script (Live)
1. Go to **Dashboard** and set **Minutes available today** (e.g., 90).
2. Show the **Today Plan** list (tasks ordered by due date urgency + balance).
3. Mark a task **Done** 􏰒 plan recomputes and remaining tasks update.
4. Go to **Assignments** 􏰒 create a new assignment due soon.
5. Click **Generate tasks** 􏰒 show tasks created in 30-min chunks.
6. Return to **Dashboard** 􏰒 show the new tasks now appear and are prioritized.

## Testing
```bash
npm run test
```

## Challenges
- Choosing a prioritization strategy that is simple but explainable in a demo.
- Keeping the system adaptive when time and progress change.

## Future Work
See `FUTURE_WORK.md`.
