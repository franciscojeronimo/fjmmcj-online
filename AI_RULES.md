# AI_RULES.md

## Purpose
These rules define how the AI agent must operate within this project.  
They ensure traceability, reversibility, and user‑controlled change management.

---

## 1. Change Logging Requirements

### 1.1 Mandatory Logging
Every modification the AI proposes or performs must be logged in a dedicated Markdown file:

CHANGELOG.md

### 1.2 Automatic Change ID
Each logged change must include a unique, automatically generated Change ID:

CHANGE-{timestamp}-{random_suffix}

Example:

CHANGE-20260726-AX4F

### 1.3 Log Entry Structure
Each entry must contain:

- Change ID  
- Timestamp (UTC)  
- Affected files  
- Summary of the change  
- Full diff (before/after)  
- Reversal instructions  
- User approval status  

Example entry (conceptual):

## CHANGE-20260726-AX4F  
Timestamp: 2026-07-26 09:14 UTC  
Files: src/app/main.py  
Summary: Refactored initialization logic  
Diff: (before/after code diff)  
Reversal: Restore previous version using stored diff  
Status: Pending user approval  

---

## 2. Reversibility Requirements

### 2.1 Every Change Must Be Reversible
The AI must never apply a modification that cannot be undone.

### 2.2 Reversal Metadata
Each change must include:

- A reversal diff  
- A reversal procedure  
- A reversal safety check  

### 2.3 No Destructive Operations
The AI is forbidden from:

- Deleting files without backup  
- Overwriting content without storing the previous version  
- Performing irreversible transformations  

---

## 3. User Approval Workflow

### 3.1 No Hard Commits
The AI must never commit changes directly to the repository.

### 3.2 Mandatory User Approval
Every change must follow this workflow:

1. AI drafts the change  
2. AI logs the change in CHANGELOG.md  
3. AI presents the change to the user  
4. User explicitly approves or rejects  
5. Only after approval, the AI may apply the change  

### 3.3 Approval Format
User approval must be explicit, for example:

APPROVED: CHANGE-20260726-AX4F

Rejection example:

REJECTED: CHANGE-20260726-AX4F

### 3.4 No Implicit Approval
Silence or lack of response never counts as approval.

---

## 4. Operational Constraints

### 4.1 Read‑Only Mode by Default
Unless a change is approved, the AI operates in read‑only analysis mode.

### 4.2 No Autonomous Refactoring
The AI must not:

- Refactor code on its own  
- Optimize code without request  
- Modify architecture without explicit instruction  

### 4.3 No Self‑Modification
The AI cannot modify:

- This rules file  
- Its own configuration  
- Its own operational logic  

Unless explicitly instructed and approved.

---

## 5. Safety & Consistency Rules

### 5.1 Deterministic Behavior
All change IDs, diffs, and logs must be generated deterministically.

### 5.2 No Hidden Changes
The AI must never:

- Make silent edits  
- Skip logging  
- Skip diff generation  

### 5.3 Transparency
All actions must be fully visible to the user.

---

## 6. Enforcement

Violating any rule results in:

- Immediate rollback  
- User notification  
- Suspension of further changes until the user re‑authorizes the agent  

---

## 7. Versioning

This file is versioned manually by the user.  
The AI may propose updates, but cannot modify it without explicit approval.
