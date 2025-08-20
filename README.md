# HandRehab+ — Mobile Rehab App for Post-Operative Hand & Upper-Extremity Care

> A patient- and therapist-facing mobile platform that drives at-home rehab adherence, measures recovery with on-device AI, and closes the loop with clinician dashboards and EHR integration. :contentReference[oaicite:0]{index=0}

---

## Overview
**HandRehab+** addresses gaps in outpatient rehabilitation by pairing **guided home exercise** with **daily symptom tracking**, **AI-assisted range-of-motion (ROM) analysis**, and a **secure provider dashboard**. The goal is to improve adherence, enable timely interventions, and support data-driven care between clinic visits. Target users are:
- **Patients** recovering from hand, wrist, or elbow surgery (e.g., thumb CMC arthroplasty)
- **Occupational/Physical Therapists** who monitor progress, adjust plans, and communicate with patients

Evidence from recent mHealth literature shows that interactive apps with **multimedia exercises**, **tracking**, **feedback loops**, and **clinician oversight** improve adherence and outcomes versus paper instructions alone. HandRehab+ implements these evidence-based features end-to-end. :contentReference[oaicite:1]{index=1}

---

## Key Features

### Patient
- **Daily assessments**: pain, grip strength, sleep, fatigue  
- **Video-guided exercises** with clear pacing and form cues  
- **AI ROM analysis (on-device)** for joint angle estimation (privacy-preserving)  
- **Progress dashboards** and **badge rewards** to motivate adherence  
- **Educational micro-lessons & quizzes** to reinforce self-management

### Provider
- **Caseload dashboard** with real-time metrics and trends  
- **AI-generated alerts** for missed sessions, rising pain, or stalled progress  
- **Plan management**: assign/adjust exercise programs, message patients  
- **Secure data sharing** into clinical workflows

> Early usability sessions (therapists + post-op patients) informed revisions such as clearer pain-scale guidance, slow-motion looping exercise videos, and streamlined quizzes. :contentReference[oaicite:2]{index=2}

---

## Screens & Workflows (Prototype)
- **Patient Home**: schedule, % recovered, reps completed, shortcuts to plans  
- **Exercise Tracker**: status by activity (Not Started/In Progress/Completed)  
- **Provider Dashboard**: caseload view, alerts, drill-downs to patient metrics  
- **Progress View**: ROM, grip, and pain trends pre/post exercise

*(Wireframes created in Figma; parallel patient/provider swim-lane flows guided IA and navigation.)* :contentReference[oaicite:3]{index=3}

---

## Architecture (High Level)
- **Mobile client**: iOS (Swift + SwiftUI) with **TensorFlow Lite** for on-device ROM analysis  
- **Backend**: HIPAA-ready AWS stack (e.g., Lambda/EC2/Kubernetes) with Node.js or Python services  
- **APIs & Auth**: OAuth 2.0 + OpenID Connect, Single Sign-On (SSO) with hospital IdP  
- **EHR Interop**: **FHIR** APIs  
  - Pull: provider assignments, surgery details  
  - Push: PGHD metrics (ROM scores, pain levels) as FHIR Observation/Communication resources  
- **Data**: validated on client/server; stored in encrypted cloud DB (e.g., RDS/DynamoDB) with timestamps and plan linkage

> A data architecture supports secure PGHD capture, therapist review, and EHR feedback loops. :contentReference[oaicite:4]{index=4}

---

## Security & Privacy (Defense-in-Depth)
- **Encryption**: TLS 1.3 in transit; AES-256 at rest (AWS KMS for key management)  
- **Access Control**: RBAC by role (patient vs. therapist), MFA for providers  
- **Session Security**: timeouts, secure token storage  
- **Auditing**: immutable logs for PHI access/changes  
- **Retention**: ephemeral handling of sensitive media (e.g., exercise videos) per policy  
- **Compliance posture**: HIPAA-aligned safeguards and periodic security reviews

:contentReference[oaicite:5]{index=5}

---

## Design & Research Notes
- Literature scan shows superior engagement/outcomes when apps combine **guided exercises**, **tracking**, **feedback**, and **therapist oversight**; simplistic, non-interactive apps underperform.  
- Task and cognitive analyses clarified requirements (e.g., basic smartphone skills, need for progress feedback, safe recording environment).  
- Accessibility from the outset: high contrast, scalable typography, large touch targets, skip options for unavailable measures, and planned voice-over/audio guidance.  
:contentReference[oaicite:6]{index=6}

---

## Usability Testing (Round 1)
- **Participants**: 2 OTs, 1 PT, 3 post-op patients  
- **Tasks**: sign-in, pre-exercise survey, guided session (optional recording), post-session quiz  
- **Scores**: avg ease-of-use ≈ **4.3/5**  
- **Top revisions**:
  - **Contextual pain anchors** (0–10 descriptors)  
  - **Slow-motion MP4 loops** to clarify hand/finger positions  
  - **Simplified quizzes** (one Q per screen, immediate feedback)  
:contentReference[oaicite:7]{index=7}

---

## Roadmap
- **Clinical validation** and pilots across diverse patient populations  
- **Expanded accessibility**: voice-to-text and text-to-voice controls  
- **Model hardening**: robust, multi-context ROM estimation with on-device ML  
- **Deeper EHR integration**: broadened FHIR resources and automated alerts  
- **Android client** parity after iOS prototype maturity  
:contentReference[oaicite:8]{index=8}

---

## Tech Stack Summary
- **Mobile**: Swift, SwiftUI, TensorFlow Lite (on-device inference)  
- **Backend**: AWS (Lambda/EC2/K8s), Node.js/Python services  
- **APIs/Interop**: OAuth2, OIDC, FHIR (Observation, Communication)  
- **Data**: RDS/DynamoDB (encrypted), PGHD intake & validation  
:contentReference[oaicite:9]{index=9}

---

## Getting Started (Prototype)
> Repo setup instructions will depend on the actual codebase structure. Typical iOS prototype steps:
1. Clone the repo & open the `.xcodeproj`/`.xcworkspace` in **Xcode**  
2. Configure any API base URLs and feature flags in app settings  
3. Build & run on a simulator or device (iOS 16+)  
4. Use mock credentials (or configure SSO sandbox) for the provider dashboard

---

## Contributors
- **Austin Cherian**, **Tsegie Kassahun**, **Maxwell Lewis** — Design & Development  
- Clinical & faculty collaborators referenced in the project report  
:contentReference[oaicite:10]{index=10}

---

## Citation
This README summarizes the **HIDS 7007 Final Project** documentation for HandRehab+. :contentReference[oaicite:11]{index=11}
