# arkit8s — Living Architecture as Code for Kubernetes/OpenShift

## Overview

**arkit8s** is a **living, executable architecture** for Kubernetes/OpenShift, defined entirely as code.  
It aims to:

- Represent an organization’s architecture using **deployable, observable components**.
- Enable a **1:1 mapping** between what is defined in Git and what is deployed in the cluster.
- Provide a **GitOps-friendly, architecture-as-code** reference for teams and organizations.

It uses **mock/dummy components** to reflect real domains and dependencies, while remaining lightweight and easy to deploy.

---

## Goals & Motivation

arkit8s was created to answer:

> “How can we make architecture not just a diagram, but something that runs, can be observed, and can be evolved safely?”

Key goals:

- Provide a **concrete, running representation** of the architecture.
- Use **Git** as the single source of truth.
- Avoid “PowerPoint architectures” that don’t match reality.
- Demonstrate good practices in:
  - Namespacing
  - Kustomize usage
  - Domain separation
  - Shared components
  - Bootstrap vs business components

---

## Core Concepts

### 1. Architecture as Code

- Every architectural building block has:
  - A **namespace**
  - **Manifests** (Deployments, Services, etc.)
  - Metadata to represent its role and dependencies.
- Resources are intended to be **deployable with `oc apply -f . --recursive`** from the repo root.

### 2. Support vs Business Domains

- Clear separation between:
  - **Business Domain** components (systems that implement business capabilities).
  - **Support Domain** components (e.g., authentication, user resolution, etc.).
- This avoids confusion around “technical” vs “business” while recognizing that all software is technical.

### 3. Shared Components

- A `shared-components/` directory contains reusable patterns (e.g., Keycloak).
- Shared components are:
  - Defined once with **base + Kustomize overlays**.
  - Instantiated from `business-domain/` or `support-domain/`.
- Prevents redundancy and keeps references consistent.

### 4. Bootstrap & Namespaces

- Bootstrap manifests (e.g., Namespaces) are kept in **separate files**, not bundled into large manifests.
- Emphasizes:
  - Clarity
  - Maintainability
  - Reduction of “orphaned” resources

---

## Platform & Tooling

- **Platform**: Designed for OpenShift, compatible with Kubernetes concepts.
- **Images**: Default / dummy images use  
  `registry.redhat.io/openshift4/ose-tools-rhel`
  - This includes dummy business components when no specific image is required.
- **Kustomize**: Used to:
  - Compose environments.
  - Manage overlays for shared components (e.g., Keycloak minimal functional config).
- **GitOps-friendly**:
  - Repository structured to work well with tools like Argo CD.
  - Emphasis on **consistency and idempotency**.

---

## Outcomes & Impact

- Provides a **deployable reference architecture** that:
  - Teams can study and adapt.
  - Shows how domains and dependencies can be modeled in Kubernetes.
- Helps:
  - Keep architecture **alive, testable, and observable**.
  - Reduce the gap between “design” and “reality”.
- Acts as a **teaching and alignment tool** in conversations about:
  - Domains
  - Dependencies
  - Platform responsibilities
  - Bootstrap vs business components

---

## Learnings

- Having a **living architecture** exposes inconsistencies early:
  - Missing dependencies.
  - Unclear contracts.
  - Overcomplicated topologies.
- Using **dummy workloads** allows teams to focus on structure before implementation details.

---

## Potential Future Work

- Observability integration as first-class citizen (dashboards for domains, dependencies, health).
- Advanced metadata (e.g., risk levels, criticality, data classification).
- Automated checks: ensure Git state and cluster state remain aligned.
