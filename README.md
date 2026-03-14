# Minor Trauma Emergency Circuit (MonoTrauma) — BPM Redesign

## Project Overview

This project applies the full **Business Process Management (BPM) Lifecycle** to redesign the Minor Trauma Emergency Circuit (MonoTrauma) at **ULS São José**, a public hospital in Lisbon, Portugal.

The goal was to reduce patient waiting times, eliminate process inefficiencies, and improve resource utilization — while keeping cost impact minimal.

---

## Problem Statement

Emergency services face increasing pressure due to growing patient volumes. The MonoTrauma circuit — a dedicated pathway for minor orthopedic trauma (limbs/vertebral) — had significant inefficiencies:

- Patients crossing departments **4–6 times** per visit
- A **radiology bottleneck** causing delays across the entire process
- Average cycle time of **2 hours 14 minutes** per patient
- Only **59 of 70 patients** completing the process per 12h shift

---

## Methodology

| Phase | Approach |
|---|---|
| Process Modelling | BPMN 2.0 — Bizagi Modeler |
| Qualitative Analysis | Value-Added Analysis (VA / BVA / NVA), Waste Analysis, Issue Register |
| Quantitative Analysis | Discrete-Event Simulation (Time, Cost, Resources) |
| Redesign Strategy | Heuristics — Re-sequencing & Parallelism |

---

## AS-IS Process

The current process flows through **4 departments** and **8 sub-processes**:

1. Admission — Registration & administrative data
2. Triage — Prioritization & MonoTrauma activation
3. Radiology: First Approach — Initial X-Ray
4. Orthopedics: First Evaluation — Diagnosis & decision
5. Radiology: X-Ray Prescriptions — Control exams
6. Orthopedic Screening — Review of control images
7. Radiology: CT Scan — Surgery planning
8. Orthopedics: Final Evaluation — Discharge or surgery admission

### AS-IS Simulation Results

| Metric | Value |
|---|---|
| Avg. Cycle Time | 2h 14m 24s |
| Throughput | 59 / 70 patients per shift |
| Orthopedist Utilization | 86.77% (bottleneck) |
| Radiology Tech Utilization | 73.26% |
| Receptionist Utilization | 23.97% (underutilized) |
| Cost per Shift | €956.20 |

---

## Issues Identified

- **Excessive waiting times** between clinical stages
- **Radiology bottleneck** — workload concentration and repetitive patient movement
- **External dependency** — delays from external CT scan reporting
- **Non-value-adding steps** — redundant patient movements and administrative tasks

---

## TO-BE Redesign — Heuristics Applied

| Heuristic | Change | Impact |
|---|---|---|
| Re-sequencing (Knock-out) | Early "Hospital Area" check filters 30% of surgical cases | Avoids unnecessary planning steps |
| Re-sequencing (Decision) | "Need Surgery?" check moved earlier | Skips redundant X-Ray prescriptions |
| Parallelism | X-Ray and CT scans run in parallel for surgical patients | Reduces lead time significantly |

---

## Final Results — AS-IS vs TO-BE

| Metric | AS-IS | TO-BE | Improvement |
|---|---|---|---|
| Avg. Cycle Time | 2h 14m 24s | 1h 14m | **~50% reduction** |
| Throughput | 59 patients | 68 patients | **+15% capacity** |
| Cost per Shift | €956.20 | €968.25 | +€12.05 (minimal) |

> The substantial gain in capacity and speed justifies the marginal cost increase.

---

## Tools & Skills

![BPMN](https://img.shields.io/badge/BPMN%202.0-Process%20Modelling-blue?style=flat)
![Bizagi](https://img.shields.io/badge/Bizagi-Modeler-purple?style=flat)
![Simulation](https://img.shields.io/badge/Discrete--Event-Simulation-teal?style=flat)
![BPM](https://img.shields.io/badge/BPM-Lifecycle-orange?style=flat)

---

## Repository Structure

```
📁 monotrauma-bpm-redesign
├── 📄 README.md
├── 📁 docs/
│   ├── AS-IS_process_report.pdf
│   └── TO-BE_process_report.pdf
├── 📁 diagrams/
│   ├── as_is_overview.png
│   ├── to_be_overview.png
│   └── sub_processes/
└── 📄 insights.md
```

---

## Key Learnings

- Process simulation with real hospital data reveals bottlenecks invisible to qualitative analysis alone
- Re-sequencing decisions earlier in a flow can eliminate entire sub-processes downstream
- Parallelism is one of the highest-impact redesign heuristics in healthcare workflows
- Structured BPM methodology can deliver significant operational improvements with minimal financial cost

---

## Academic Context

This project was developed as part of the **MSc in Information Management (Digital Transformation)** at NOVA IMS, Lisbon.

**Organization:** ULS São José — Lisbon, Portugal
