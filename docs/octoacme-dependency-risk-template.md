# Dependency & Risk Management Template

## Purpose
Provide a standardized approach to identifying, tracking, and escalating cross-team dependencies and risks throughout the project lifecycle.

## Dependency Types

### Internal Dependencies
**Definition:** Work items that depend on other work items within the same team or project.

**Examples:**
- Backend API development must complete before frontend integration
- Database schema must be finalized before ORM model implementation
- Design mockups must be approved before development begins

**Management:**
- Document in backlog with clear "blocking" relationships
- Review in sprint planning to sequence work
- Flag in daily standup if blocking path changes

---

### External Dependencies
**Definition:** Work items that depend on other teams, systems, or third-party services.

**Examples:**
- Awaiting API from Partner Team before integration work begins
- Waiting for infrastructure provisioning from DevOps
- Third-party service upgrade scheduled for specific date
- Security approval before feature release
- Legal review of privacy policy language

**Management:**
- Owner identified and explicitly accountable for resolving
- Target completion date documented in risk register
- Weekly dependency sync with external team lead
- Escalation path defined if dependency at risk

---

### Architectural Dependencies
**Definition:** Technical decisions or design patterns that multiple teams must coordinate on.

**Examples:**
- Microservice interface design
- Authentication/authorization approach
- Data schema shared across systems
- Shared infrastructure or resource limits
- Technology stack decisions

**Management:**
- Technical Lead owns coordination
- Architecture Decision Record (ADR) documented
- Review across all impacted teams
- Change management process for updates

---

## Dependency Register

### Template

| ID | Description | Type | Owner | Target Date | Status | Blocker? | Notes |
|-----|-----------|------|-------|-------------|--------|---------|-------|
| D-001 | Backend API complete before mobile client integration | Internal | Dev Lead | Sprint 3 EOW | On Track | No | API design doc in review |
| D-002 | Security approval on OAuth implementation | External | PM | 2 days | At Risk | Yes | Awaiting Security Officer | 
| D-003 | Database schema finalized for analytics work | Architectural | Tech Lead | Sprint 2 EOW | Complete | No | Approved in design review |

### Key Fields Explained

- **ID:** Unique identifier (D-001, D-002, etc.)
- **Description:** What is being depended on?
- **Type:** Internal, External, or Architectural
- **Owner:** Who is accountable for this dependency?
- **Target Date:** When must this be resolved?
- **Status:** On Track, At Risk, Blocked, Complete
- **Blocker?:** Does this block other work? (Yes/No)
- **Notes:** Latest update, action items, contact info

---

## Dependency Management Process

### 1. Identification Phase (Planning)
- **When:** Project planning and sprint planning sessions
- **Who:** Product Manager, Technical Lead, Project Manager
- **How:**
  - Review backlog for cross-team dependencies
  - Ask: "What must be true for this to work?"
  - Identify external teams or services required
  - Document in dependency register with target dates

### 2. Tracking Phase (Execution)
- **When:** Weekly dependency sync + daily standups
- **Cadence:**
  - Daily standup: Mention if dependency status changed
  - Weekly: Update dependency register with all owners
  - Weekly: Cross-team sync for critical dependencies
- **How:**
  - Status updates: On Track, At Risk, Blocked
  - Owner takes action if status degrades
  - Escalate if dependency at risk of missing target date

### 3. Escalation Phase
- **Level 1:** Owner resolves within their team or with direct contact
- **Level 2:** Project Manager escalates to external team lead or product lead (if internal)
- **Level 3:** Sponsor escalates to executive leadership (if organizational blocker)

### Escalation Triggers
- ⚠️ **Escalate immediately if:**
  - Dependency at risk of missing target date by >2 days
  - Dependency is blocking critical path work
  - External team unavailable or non-responsive
  - Architectural decision contested by multiple teams

---

## Risk Register

### Template

| ID | Risk | Impact | Likelihood | Owner | Mitigation | Status | Target Close |
|-----|------|--------|-----------|-------|-----------|--------|--------------|
| R-001 | Key engineer unavailable mid-sprint | High | Medium | PM | Cross-train backup; document code | Active | End of sprint |
| R-002 | Third-party API change breaks integration | High | Low | Tech Lead | Monitor API changelog; versioning strategy | Active | Sprint 3 |
| R-003 | Scope creep from Stakeholder feedback | Medium | High | PM | Weekly scope review; formal change control | Active | Ongoing |

### Key Fields Explained

- **ID:** Unique identifier (R-001, R-002, etc.)
- **Risk:** What could go wrong?
- **Impact:** What happens if it occurs? (High/Medium/Low)
- **Likelihood:** How likely is it? (High/Medium/Low)
- **Owner:** Who is accountable for monitoring and mitigating?
- **Mitigation:** What actions reduce the risk?
- **Status:** Active, Mitigated, Escalated, Resolved
- **Target Close:** When should this risk be closed or re-evaluated?

---

## Risk Assessment Matrix

```
         High Likelihood
              |
              |    🔴 R-003    🔴 R-005
Medium        |  (Med Impact)  (High Impact)
Likelihood    |
              |    🟡 R-001    🟡 R-002
              |  (Low Impact)  (Med Impact)
              |________________
                Low Likelihood

Impact: Low ← → High
```

**Color Coding:**
- 🔴 **RED (Critical):** High Impact + High Likelihood → Escalate immediately, implement contingency plan
- 🟠 **ORANGE (Major):** High Impact + Medium Likelihood → Active mitigation required
- 🟡 **YELLOW (Minor):** Medium/Low Impact or Low Likelihood → Monitor regularly; mitigation planned
- 🟢 **GREEN (Low):** Low Impact + Low Likelihood → Track but lower priority

---

## Risk Management Lifecycle

### 1. Identification (Planning Phase)
- **When:** Project initiation and sprint planning
- **Who:** Full team brainstorm with PM facilitation
- **How:**
  - "What could prevent us from delivering?"
  - "What assumptions are we making?"
  - "What dependencies could fail?"
  - Document in risk register with impact & likelihood

### 2. Assessment (Ongoing)
- **Cadence:** Weekly risk register review
- **Who:** Project Manager + risk owners
- **How:**
  - Reassess impact and likelihood based on progress
  - Move risks to "Mitigated" or "Resolved" if conditions improve
  - Add new risks if identified
  - Escalate if risk materializes or probability increases

### 3. Mitigation (Execution)
- **Owner executes mitigation plan:**
  - Contingency planning (Plan B if risk occurs)
  - Preventive actions (reduce likelihood)
  - Reactive actions (reduce impact if it occurs)
- **Track progress in risk register**

### 4. Escalation (If Risk Activates)
- **Level 1:** Owner addresses with team (standup discussion)
- **Level 2:** PM escalates to Product Lead if major impact (scope, timeline, quality)
- **Level 3:** Sponsor engaged if business outcome at risk

### 5. Resolution/Closure
- **When:** Risk is eliminated, target date passes, or contingency activated
- **How:** Update risk register; capture lessons for retrospective

---

## Dependency & Risk Communication

### Weekly Status Report Template

```
**Dependency Status:**
- D-001 (Backend API): ✅ On Track - PR merged; integration work starting
- D-002 (Security Approval): ⚠️ At Risk - Awaiting response from Security Officer (2 days overdue)
  - Action: PM following up with Security Lead; may request escalation

**Risk Status:**
- R-001 (Key Engineer Unavailable): 🟡 Active - Cross-training in progress
- R-002 (Third-party API Change): 🟢 Resolved - API versioning implemented; no longer a risk
- R-003 (Scope Creep): 🟡 Active - Formal change control process established

**Escalations Needed:**
- Requesting Sponsor decision on scope change proposed by Stakeholder (impacts timeline)
```

### Meeting Cadence

| Meeting | Frequency | Participants | Focus |
|---------|-----------|--------------|-------|
| Daily Standup | Every day (15 min) | Team + PM | Quick dependency/risk flag updates |
| Weekly Sync | Once per week | Core team + Tech Lead | Detailed dependency & risk review |
| Cross-Team Sync | As needed | PM + external team leads | Coordinate on external dependencies |
| Escalation Review | On-demand | PM + Product Lead + Tech Lead | Handle RED or escalated items |

---

## Escalation Paths

### Dependency Escalation
```
Owner cannot resolve within 24 hours
         ↓
PM escalates to external team lead or Product Lead
         ↓
If no resolution within 48 hours, Sponsor engages
         ↓
Sponsor works with external org leadership
         ↓
Timeline/scope adjusted if dependency cannot be met
```

### Risk Escalation
```
Risk materializes or likelihood increases significantly
         ↓
Owner flags in standup; PM documents status change
         ↓
PM assesses impact to timeline/quality/scope
         ↓
If high impact, PM escalates to Product Lead / Sponsor
         ↓
Team decides: proceed with contingency, adjust scope, or delay
```

---

## Success Metrics

- **Dependency tracking:** 100% of cross-team dependencies documented before sprint starts
- **Dependency resolution time:** Average resolution time ≤ 5 business days
- **Risk escalation response:** Critical risks escalated within 4 hours; resolved within 48 hours
- **At-risk items:** Caught and escalated before blocking critical path
- **Retrospective learning:** Risk mitigation improvements captured and applied to future projects

---

## References
- `octoacme-project-planning.md` - Planning phase dependency identification
- `octoacme-execution-and-tracking.md` - Execution cadence and blocker escalation
- `octoacme-risks-and-communication.md` - Risk communication templates
- `octoacme-cross-functional-collaboration.md` - Cross-team coordination patterns

