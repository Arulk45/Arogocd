# GitOps Deployment with ArgoCD

## Overview
This document describes the GitOps deployment model implemented using ArgoCD for Kubernetes application delivery, configuration management, and drift reconciliation.

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
