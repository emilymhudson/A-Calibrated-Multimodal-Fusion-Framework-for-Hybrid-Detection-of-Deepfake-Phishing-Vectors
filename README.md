%%writefile README.md
# A Calibrated Multimodal Fusion Framework for Hybrid Detection and Enterprise Defensive Orchestration of Deepfake Phishing Vectors

## Overview
The detection system is an advanced, multimodal AI driven architecture engineered to detect malicious email communications containing deepfake payloads. By utilizing a late-fusion ensemble approach, it analyzes header, linguistic, visual, and acoustic features simultaneously to provide a calibrated, high-fidelity threat severity score.

## Architecture & Pipeline
The system operates on a highly optimized, multi-layer processing pipeline:
- **Layer 1 (Deterministic MIME Parser):** Decomposes raw .eml or .msg files, isolating headers, text bodies, and multimedia attachments (images/video/audio) into independent, modality-specific processing streams.
- **Layer 2 (Feature Extraction):** Uses frozen foundational models for deterministic feature extraction:
  - *Linguistic Track*: DistilBERT (Intent Mapping)
  - *Visual Track*: EfficientNet-B7 (Artifact Extraction)
  - *Acoustic Track*: Wav2Vec 2.0 (Forensic Countermeasures)
  - *Header Track*: Rule-Based Compliance Engine
- **Layer 3 (Calibration):** Implements Platt Scaling (via Logistic Regression with Variance Scaling) to ensure accurate probability representations and mitigate model overconfidence.
- **Layer 4 (Late Fusion):** A supervised fusion engine that evaluates the calibrated modalities against one another to output a final `P_final` threat probability.
- **Layer 5 (Severity Routing):** Operational triage that quantizes the continuous threat probability into discrete severity tiers:
  - *Severity 1*: Silent Drop (Automated Suppression Vector)
  - *Severity 2-3*: Low/Medium-Priority Analyst Dashboard (Inspection Vector)
  - *Severity 4-5*: High/Critical Alert SIEM Push (Escalation Vector)

## Environment Setup
1. **Cold Storage Mount**: Mount Google Drive to access raw massive multimodal datasets (Enron, EPVME, FaceForensics++, OpenForensics, ASVspoof).
2. **Hot Storage Staging**: Execute the deterministic extraction engine to transfer and unpack assets onto the localized fast NVMe SSD (`/content/hot_storage`) to prevent I/O bottlenecks.
3. **Combinatorial Testbed**: Generate the 1,000-sample multimodal testbed mapping header, text, audio, and visual attachments to verified ground-truth labels.

## Empirical Performance
Based on a stratified 5-Fold Nested Cross-Validation over 1,000 multimodal assets:
- **Master Cross-Validated Accuracy**: ~92.90%
- **Master Global ROC-AUC**: ~0.916
- **Queue Redirection Rate (QRR)**: ~55.10% (Alerts successfully suppressed from Tier-1 queues)
- **Δ False Negative Rate (Safety Constraint)**: Maintained strictly under operational tolerances.

## Legal & Licensing Notice

**Open Source Code License (MIT)**
The source code within this project is licensed under the MIT License. You are free to use, modify, distribute, and build upon the code for both commercial and non-commercial purposes, provided you include the original copyright and license notice in any substantial portions of the software.

**Trademark & Branding Notice**
The brand name **"Praxis Detection System"**, along with any associated logos, graphics, and trade dress, are the exclusive property and trademarks of the project creator. 

*While the underlying codebase is open-source, this license does **not** grant you the right to use the "Praxis Detection System" name, branding, or identity to market, endorse, or promote your own derived products, services, or clones. Any public use of the brand name requires explicit, prior written permission.*
