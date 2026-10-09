# CPU Scheduling Simulator

A React + Vite app (JavaScript, shadcn/ui, Tailwind v4) that simulates two
non-preemptive CPU scheduling algorithms — **FCFS** and **SJF** — and reports
each process's completion, turnaround, and waiting time, plus averages.
Built for Machine Problem #2 (Operating System).

## Getting started

```bash
npm install
npm run dev
```

Then open the printed local URL (usually `http://localhost:5173`).

To build for production:

```bash
npm run build
npm run preview
```

## How it works

1. **Set the number of processes** (3-10).
2. **Enter each process's ID, arrival time, and burst time.** Inputs are
   validated: IDs must be non-blank and unique, arrival time must be a whole
   number >= 0, and burst time must be a whole number >= 1.
3. **Choose FCFS or SJF** and click **Compute**.
4. Results show a Gantt-style execution timeline, a per-process table
   (completion / turnaround / waiting time), and the averages.

SJF here is non-preemptive: at any idle moment it picks the shortest burst
among processes that have already arrived, and ties are broken by earliest
arrival then by original input order (falls back to FCFS behavior on ties,
per the assignment spec). The scheduling logic itself lives in
`src/lib/scheduling.js` if you want to inspect or extend it.

## Theme

Light/dark mode is toggled from the header (saved to `localStorage`) and
uses the exact shadcn design tokens from `src/index.css`.

## Tech stack

- React 19 + Vite
- Tailwind CSS v4
- shadcn/ui primitives (Button, Input, Select, Card, Table, Switch, Alert)
- lucide-react icons
