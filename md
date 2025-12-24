# GitOps Deployment with ArgoCD

## Overview
This document describes the GitOps deployment model implemented using ArgoCD for Kubernetes application delivery, configuration management, and drift reconciliation.

**GitOps with ArgoCD — Documentation**
1. What is GitOps?

GitOps is an operational framework that:

Uses Git as the single source of truth for infrastructure and application state

Ensures deployments are declarative, versioned, and auditable

Relies on automation agents to continuously reconcile desired vs actual state

**Core Principles**

Declarative → Desired state stored as code (YAML/Helm/Kustomize/JSON)

Versioned & Immutable → Every change is committed, tagged, traceable

Pulled Automatically → CD agents apply changes from Git (no manual kubectl)

Continuously Reconciled → System auto-heals drift

Auditable → Git history = compliance + rollback source

**2. Why ArgoCD for GitOps?**

ArgoCD is a declarative GitOps CD controller for Kubernetes that:

Pulls manifests from Git repositories

Syncs them into Kubernetes clusters

Detects and corrects configuration drift

Provides UI, CLI, API, RBAC, SSO, notifications, and health checks



## Core Capabilities
- Declarative application state management
- Automated synchronization and self-healing
- Git as the single source of truth
- Audit trail and rollback via version control
- Multi-environment promotion (Dev → Staging → Prod)

## Architecture

Developer → commits code/manifests → GitHub Repo
                         ↓
                 ArgoCD (pull model)
                         ↓
      Compares Desired State (Git) vs Actual State (Cluster)
                         ↓
    Syncs changes OR auto-heals drift (Reconciliation Loop)
                         ↓
                Kubernetes Cluster
