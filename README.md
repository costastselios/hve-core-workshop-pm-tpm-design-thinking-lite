# HVE Core workshop: saved packs

Saved runs of the [HVE Core idea-to-backlog workshop](https://github.com/costastselios/hve-core-pm-tpm-design-thinking-workshop), made with the real HVE Core agents (DT Coach, BRD Builder, PRD Builder). Each pack lets every pair continue from the same point.

> **All data in these packs is made up** (a fictional investor and fictional portfolio). There is no real personal or financial information.

## The two packs everyone uses

| When | Pack | Download |
|---|---|---|
| **12:00** | **Pack A**: Design Thinking state after research and synthesis (Steps 2–3), used for the Step 4 brainstorm | [Pack-A-after-Step-3.zip](https://github.com/costastselios/hve-core-workshop-reference/raw/main/Pack-A-after-Step-3.zip) |
| **14:40** | **Pack D**: approved BRD and PRD, used for the guided read and Step 9 | [Pack-D-after-Step-8.zip](https://github.com/costastselios/hve-core-workshop-reference/raw/main/Pack-D-after-Step-8.zip) |

**How to load (both packs):**
- Unzip the pack. **Mac:** double-click. **Windows:** right-click → **Extract All…** → **Extract**.
- Each pack contains a `README.md`, a screenshot and **one folder to drag**. Nothing is hidden.
- **Golden rule:** if VS Code ever asks **"Replace?"**, click **Cancel**.

## Pack A: load at 12:00

**Download:** https://github.com/costastselios/hve-core-workshop-reference/raw/main/Pack-A-after-Step-3.zip

**Drag (one sentence):** Drag the **`pack-a`** folder from the unzipped pack onto the **empty space at the bottom of the VS Code file panel**, so it lands at the top level next to `docs` and `workshop`.

![Drag pack-a onto the empty space at the bottom of the VS Code file panel](pack-a-drag.png)

**Check:** the VS Code file panel now shows a top-level folder **`pack-a`**. Open it to see `pack-a › dt › portfolio-tracker › coaching-state.md`. Your own Step 1 files in `.copilot-tracking` are untouched.

**Resume (new chat):**
1. Open a **new** Copilot Chat and pick **DT Coach**. Don't continue your Step 1 chat.
2. Attach `pack-a/dt/portfolio-tracker/coaching-state.md` with **Add Context** or by dragging the file into the chat.
3. Paste:

```text
Resume the Design Thinking project saved in pack-a/dt/portfolio-tracker/ and keep saving its files there. Read coaching-state.md and the Method 1–3 artifacts it lists. Summarize only the state you can access, in at most 8 short bullets: methods completed, the evidence and its confidence (P01 and P02 kept separate), the opportunity frame, my Product Owner decisions, and the open questions. Do not reconstruct missing evidence and make no prevalence claims. Then stop and wait: I will start Method 4 (Workshop Step 4 — Brainstorming) in my next message.
```

**You should see:** about 8 bullets (Methods 2–3 complete for the workshop, P01/P02 kept separate at low confidence, the opportunity frame, Product Owner decisions, open questions), ending with Method 4 *not started* and *waiting*. Then, in the **same chat**, paste the Step 4 brainstorm prompt.

**Fallback, if dragging doesn't work:** open **VS Code → Terminal → New Terminal** (it opens at your repo root) and paste one line.
- **Mac:**
  ```bash
  cp -R ~/Downloads/Pack-A-after-Step-3/pack-a .
  ```
- **Windows (PowerShell; if the prompt doesn't start with `PS`, type `powershell` first):**
  ```powershell
  $pack='Pack-A-after-Step-3'; $s=(Get-ChildItem "$HOME\Downloads" -Directory -Recurse -Depth 3 -Filter pack-a -ErrorAction SilentlyContinue | Where-Object FullName -like "*$pack*" | Select-Object -First 1).FullName; if (-not (Test-Path workshop)) { 'STOP: run this in the VS Code terminal of your workshop repo (the folder with docs, workshop, workshop-output)' } elseif (-not $s) { "STOP: unzip $pack into your Downloads folder first" } else { robocopy "$s" pack-a /E /NFL /NDL /NJH /NJS /NP; if ($LASTEXITCODE -lt 8) { "OK - copied from $s" } else { "ERROR: robocopy exit code $LASTEXITCODE" } }
  ```
  Expected output: one line starting `OK - copied from`.

---

## Pack D: load at 14:40

**Download:** https://github.com/costastselios/hve-core-workshop-reference/raw/main/Pack-D-after-Step-8.zip

**Drag (one sentence):** Drag the **`project-planning`** folder from the unzipped pack **onto the `docs` folder** in the VS Code file panel.

![Drag project-planning onto the docs folder](pack-d-drag.png)

**Check:** the VS Code file panel now shows **`docs › project-planning`** with 4 files:
- `portfolio-tracker-brd.md`: the approved BRD
- `portfolio-tracker.md`: the approved PRD, the file for Step 9
- `portfolio-tracker-brd-to-prd-handoff.md`
- `portfolio-tracker-brd-v0.1.0.md`

If `project-planning` appears at the top level instead of inside `docs`, drag it onto `docs`.

**Guided read:** follow the "Where to look" table in the `README.md` inside the Pack D zip. Its line numbers match these files.

**Step 9 (new chat, 15:05):**
1. Open a **new** Copilot Chat and pick **PRD Builder**.
2. Attach `docs/project-planning/portfolio-tracker.md`, `docs/WORKED-EXAMPLES.md` and `docs/ARTIFACT-CHECKLIST.md`.
3. Paste:

```text
The attached file is the approved PRD planning baseline (PRD-2026-Q4-001 v1.0.0, approved as the workshop product planning baseline for Epic/Feature decomposition). It includes its inherited exclusions and open gates GATE-001 to GATE-007. Do not rely on any earlier chat.

Create a planning-only Epic/Feature proposal from that baseline:
- Epics are outcomes; Features are capabilities. Epics and Features only — no Stories, Tasks, architecture, estimates, RPI or code.
- Every Feature traces to the PRD FR IDs (and through them to BR IDs) in the approved baseline.
- Deferred and excluded scope stays out (trading, advice, forecasts, tax reporting, goal tracking, real personal financial data; composition breakdown and main-screen FX remain deferred alternatives, not Features).
- Gated capabilities stay conditional: mark each affected Feature "conditional on GATE-00x" and show the gate status (Open). Don't close any gate.
- Do not edit the approved PRD. Do not hand off to a tracker or Functional Planner, and do not start a new PRD.
Save the proposal as docs/project-planning/portfolio-tracker-epic-feature-proposal.md and show me a short summary.
```

**You should see:** a new file, `docs/project-planning/portfolio-tracker-epic-feature-proposal.md`, with about 3 Epics and 12 Features. Each Feature traces FR → BR and is marked "conditional on GATE-…" (Open). The PRD is unchanged. Names and numbers will differ between pairs, and that's normal.

**Fallback, if dragging doesn't work:** open **VS Code → Terminal → New Terminal** and paste one line.
- **Mac:**
  ```bash
  cp -R ~/Downloads/Pack-D-after-Step-8/project-planning docs/
  ```
- **Windows (PowerShell):**
  ```powershell
  $pack='Pack-D-after-Step-8'; $s=(Get-ChildItem "$HOME\Downloads" -Directory -Recurse -Depth 3 -Filter project-planning -ErrorAction SilentlyContinue | Where-Object FullName -like "*$pack*" | Select-Object -First 1).FullName; if (-not (Test-Path workshop)) { 'STOP: run this in the VS Code terminal of your workshop repo (the folder with docs, workshop, workshop-output)' } elseif (-not $s) { "STOP: unzip $pack into your Downloads folder first" } else { robocopy "$s" docs\project-planning /E /NFL /NDL /NJH /NJS /NP; if ($LASTEXITCODE -lt 8) { "OK - copied from $s" } else { "ERROR: robocopy exit code $LASTEXITCODE" } }
  ```

---

## Optional references

You don't need these packs for the workshop. They show the rest of the same saved run.

| Pack | Contents | Download |
|---|---|---|
| Pack B | Design Thinking Methods 4–6, the DT→BRD handoff and a sample prototype self-test | [Pack-B-after-Step-6.zip](https://github.com/costastselios/hve-core-workshop-reference/raw/main/Pack-B-after-Step-6.zip) |
| Pack C | Approved BRD with BRD Builder's handoffs and quality records | [Pack-C-after-Step-7.zip](https://github.com/costastselios/hve-core-workshop-reference/raw/main/Pack-C-after-Step-7.zip) |
| Pack E | An example Epic/Feature proposal from Step 9, useful to compare with yours | [Pack-E-after-Step-9.zip](https://github.com/costastselios/hve-core-workshop-reference/raw/main/Pack-E-after-Step-9.zip) |

These use an older layout. Load them with the Terminal commands in the `README.md` inside each zip.
