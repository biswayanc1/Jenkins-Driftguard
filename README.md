🚨 Jenkins DriftGuard

Automated drift detection and remediation system for Kubernetes clusters using Jenkins and GitOps principles.


🚀 Overview

In a GitOps workflow, your Git repository acts as the **source of truth** for your Kubernetes cluster configuration. But sometimes manual changes sneak into the cluster — during emergencies, debugging, or misconfigurations. This leads to **drift** — a mismatch between Git and the live cluster.

**Jenkins DriftGuard** solves this by:
- Continuously detecting drift between Git and the cluster
- Automatically restoring the correct state from Git

---

⚙️ How It Works

1. **Jenkins Pipeline** is triggered periodically or via webhook.
2. **Drift Detection Script** compares the current cluster state with Git manifests (via `kubectl diff` or `helm diff`).
3. If drift is detected:
   - Jenkins logs the differences
   - The pipeline re-applies the correct configuration from Git
4. The cluster is brought back to the **desired state**.

---
