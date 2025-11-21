# PulseState — Availability Reporting & Visualization

## Overview

PulseState is a **Quarkus-based system** that processes CSV files with availability data and generates **availability reports** that are:

- Aggregated by **day** and by **hour**
- Visualized in a **web frontend using Chart.js**
- Continuously updated via **scheduled jobs in OpenShift**

It was designed as a **practical, production-like system** to showcase:

- Clean architecture inside Quarkus
- Scheduled ingestion workflows
- Clear visual feedback with charts and filtering
- Realistic observability, caching, and health checks

---

## Context & Motivation

I wanted a system that:

- Feels like a **real operations tool**, not a toy.
- Is small enough to build and iterate quickly.
- Includes **backend, frontend, jobs, and integrations**.
- Demonstrates how to structure a Quarkus project for maintainability.

PulseState connects well with my interests in:

- **Platform engineering** (running jobs, integrating with OpenShift)
- **Observability and availability**
- **UX for operational insights**

---

## Problem Statement

> “How can we continuously ingest availability metrics from CSV files, aggregate them into meaningful views by day and hour, and present them in an intuitive, drill-down visualization for teams?”

Key needs:

- Automated ingestion of CSV files.
- Aggregation and grouping logic (daily and hourly).
- Clear visual representation of % of downtime / availability.
- Simple enough to deploy and run on OpenShift.

---

## Solution & Architecture

### Backend

- Built with **Quarkus 3.23** and **Java 21**.
- Structured following a **UbiDev-style package organization**:
  - `bootstrap`
  - `core`
  - `integration`
  - `health`
  - `web`
  - `util`
- Includes:
  - **Qute templates** for server-side rendered views.
  - **ReportCache** for optimized access to computed reports.
  - Custom **health checks** to reflect data freshness or issues.

### Data Ingestion

- Availability data is provided via **CSV files**.
- A **CronJob in OpenShift** runs every few minutes to:
  - Publish new CSV files.
  - Notify via Teams when needed.
- The system always generates a report, even if the value is **0% downtime**.

### Frontend

- Visualization using **Chart.js**.
- Main views:
  - **Daily view**: one bar (or point) per day with overall availability / downtime.
  - **Hourly view**: drill-down into a specific day to see hourly aggregation.
- Interactions (in the evolved version):
  - Click on a point/day → navigate to the detailed view for that day.
  - Click on an hour label → filter data to ±30 minutes around that hour.
  - Button to go **back from hourly view to daily view**.

---

## Tech Stack

- **Backend**: Quarkus 3.23, Java 21
- **Frontend**: Chart.js, Qute templates
- **Platform**: OpenShift (CronJobs, containers, routes)
- **CI/CD**: GitHub Actions
- **Notifications**: Integration with Teams for CSV publication and status

---

## Outcomes & Impact

- Demonstrated:
  - How to structure a Quarkus project with **clear domains and responsibilities**.
  - How to integrate with **OpenShift CronJobs** for scheduled tasks.
  - How to provide **useful, intuitive UX for operational data**.
- Served as a:
  - **Reference implementation** for similar reporting tools.
  - **Demo asset** for platform and delivery discussions.
  - Practical playground for **adding interactivity and UX refinements**.

---

## Learnings

- Small, focused systems like PulseState are ideal for:
  - Teaching architectural concepts.
  - Experimenting with UX and interactivity.
  - Demonstrating end-to-end flows (data ingestion → processing → visualization).
- Having a clear package and domain structure pays off as features are added (e.g., interactive filters).

---

## Potential Future Work

- Export capabilities (CSV, PDF, etc.).
- Alerting based on thresholds.
- Multi-source ingestion and correlation (e.g., by service, region, or environment).
- Integration with broader observability stacks.
