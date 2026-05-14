# OctoAcme — Quality Assurance & Testing Checklist

## Pre-Sprint Quality Planning

### Definition of Done Review
- [ ] Team agrees on acceptance criteria for all user stories
- [ ] Non-functional requirements documented (performance, security, accessibility)
- [ ] Test types identified (unit, integration, end-to-end, manual)
- [ ] Risk-based testing approach defined (what to test, what to skip)

### QA Resource Planning
- [ ] QA Lead estimates testing effort for sprint
- [ ] Test environment is available and prepared
- [ ] Test data sets prepared (realistic, diverse, edge cases)
- [ ] Automated test framework ready (if applicable)
- [ ] Manual testing team assigned and available

### Risk-Based Testing Strategy
- [ ] High-risk areas identified (complex logic, critical flows, security-sensitive)
- [ ] Test coverage allocated to high-risk areas
- [ ] Regression test suite prioritized (critical vs. nice-to-have)
- [ ] Edge cases and error scenarios documented

---

## During-Sprint Quality Activities

### Development Phase Quality Gates
- [ ] Unit tests written before or alongside code (TDD where practical)
- [ ] Code review includes testability assessment
- [ ] Technical Lead reviews design for test architecture
- [ ] QA Lead participates in design review (by request)

### Test Development & Execution
- [ ] Acceptance tests written from user story acceptance criteria
- [ ] Integration tests cover dependencies and data flows
- [ ] Automated tests run in CI pipeline (on every commit)
- [ ] Manual test cases executed on development branch
- [ ] Test results tracked and defects logged with reproducible steps

### Defect Management
- [ ] Defects logged with: Steps to reproduce, Expected vs. Actual, Screenshots/logs
- [ ] Severity assigned: Critical (blocks functionality), High (degrades UX), Medium, Low
- [ ] Priority assigned: Fix now vs. fix later vs. defer to future release
- [ ] Owner assigned (Developer responsible for fix)
- [ ] Target resolution date set (based on severity/priority)

### Quality Metrics Tracking
- [ ] Test coverage % (% of code covered by automated tests)
- [ ] Defect count by severity (Critical, High, Medium, Low)
- [ ] Defect resolution rate (% closed vs. outstanding)
- [ ] Test execution status (% passing, failing, blocked)
- [ ] Time-to-fix by severity (average days to close defect)

---

## Pre-Release Quality Sign-Off

### Feature Acceptance Sign-Off
- [ ] All acceptance criteria met and verified by QA
- [ ] No known critical or high-severity defects
- [ ] Edge cases and error scenarios tested
- [ ] User documentation reviewed against feature behavior
- [ ] Product Manager sign-off obtained

### Performance & Load Testing
- [ ] Response times meet SLA requirements
- [ ] Load test conducted (expected user load)
- [ ] Database queries optimized (no N+1 problems)
- [ ] Memory usage profiled (no leaks detected)
- [ ] Performance metrics documented for monitoring

### Security Testing
- [ ] OWASP Top 10 vulnerabilities scanned (or tool used: e.g., Snyk, Sonarqube)
- [ ] No critical or high-severity vulnerabilities
- [ ] Security Officer review completed
- [ ] Secrets (API keys, credentials) not in code
- [ ] Sensitive data handling reviewed (encryption, logging, PII)

### Accessibility & Usability
- [ ] Keyboard navigation works (tab through all controls)
- [ ] Screen reader compatible (tested with NVDA, JAWS, or VoiceOver)
- [ ] Color contrast meets WCAG AA standard
- [ ] Error messages are clear and actionable
- [ ] UX tested with target users (if applicable)

### Cross-Browser & Device Testing
- [ ] Desktop browsers tested (Chrome, Firefox, Safari, Edge - latest 2 versions)
- [ ] Mobile browsers tested (iOS Safari, Chrome Mobile)
- [ ] Tablet support verified (if applicable)
- [ ] No console errors or warnings

### Regression Testing
- [ ] Regression test suite executed (automated where possible)
- [ ] No previously-working features broken
- [ ] Related features tested (e.g., if auth changed, test all secure features)

### Integration & End-to-End Testing
- [ ] Feature integrated with existing system (staging environment)
- [ ] Data flows correctly through system
- [ ] Third-party integrations (APIs, services) working
- [ ] End-to-end user flows tested from start to finish

### Documentation & Runbook
- [ ] User documentation is accurate and complete
- [ ] Release notes include feature description, known issues, migration steps
- [ ] Support team briefed on new feature (FAQ, common issues)
- [ ] Rollback procedure documented and tested
- [ ] Runbook reviewed by Ops/DevOps team

---

## Release Day Quality Verification

### Pre-Deployment Checks
- [ ] Smoke test suite prepared (critical paths only; can run in <10 min)
- [ ] Deployment environment validated (connectivity, credentials, disk space)
- [ ] Backup/rollback procedure confirmed
- [ ] Monitoring and alerting configured for new feature

### Post-Deployment Verification
- [ ] Smoke tests executed in production (or staging that mirrors production)
- [ ] Critical user paths tested end-to-end
- [ ] System performance monitored (no degradation)
- [ ] Error rate monitoring active (alert thresholds set)
- [ ] Business metrics dashboard updated (e.g., signup rate, conversion)

### Incident Response Ready
- [ ] Incident response team on-call (PM, Tech Lead, Ops)
- [ ] Rollback plan is documented and practiced
- [ ] Communication plan ready (what to tell customers if issue arises)
- [ ] Post-mortem process defined (if incident occurs)

---

## Post-Release Quality Activities

### Monitoring & Observability
- [ ] Application performance metrics tracked (response time, error rate, throughput)
- [ ] User feedback monitored (support tickets, user analytics)
- [ ] Error logs reviewed (any unexpected errors in production?)
- [ ] Alert thresholds adjusted based on baseline data
- [ ] Weekly review of production metrics

### Bug Triage & Prioritization
- [ ] Production bugs triaged within 4 hours
- [ ] Critical bugs (user-facing, data loss risk) get hotfix
- [ ] High bugs scheduled for next sprint
- [ ] Medium/Low bugs added to backlog for prioritization

### Root Cause Analysis (Post-Incident)
- [ ] If production incident: What went wrong?
- [ ] How did it get past QA? (testing gap identified)
- [ ] What systemic improvement needed? (process, tooling, training)
- [ ] Preventive measures added to future DoD (e.g., new test case)

### Retrospective & Continuous Improvement
- [ ] Team retrospective: What went well? What could improve?
- [ ] QA-specific improvements captured (test coverage, tooling, process)
- [ ] Action items assigned and tracked
- [ ] Lessons applied to next sprint's quality planning

---

## Quality Roles & Responsibilities

### QA Lead
- Owns test strategy and coverage
- Leads test planning and execution
- Manages quality metrics and defect triage
- Escalates quality risks and blockers
- Facilitates quality discussions in cross-functional meetings
- Sign-off on release readiness

### Developers
- Write unit tests alongside code
- Participate in test planning and design review
- Reproduce and fix defects assigned to them
- Ensure code is testable (e.g., dependency injection, mocking support)
- Review and update acceptance criteria clarity

### Tech Lead
- Reviews test architecture and automation approach
- Ensures non-functional requirements (performance, security) covered
- Participates in performance and security testing
- Mentors team on testing best practices
- Identifies technical risks that require testing focus

### Product Manager
- Defines acceptance criteria clearly
- Participates in test planning
- Validates feature acceptance (does it meet the need?)
- Provides customer perspective on edge cases
- Prioritizes bugs and determines what gets fixed vs. deferred

### Project Manager
- Ensures QA resources allocated
- Tracks quality metrics and test progress
- Escalates quality risks and missed deadlines
- Facilitates communication between QA and other teams
- Manages release quality gate decision

---

## Quality Metrics & Targets

| Metric | Definition | Target | Frequency |
|--------|-----------|--------|-----------|
| **Test Coverage** | % of code covered by automated tests | ≥ 80% for critical paths; ≥ 60% overall | Per sprint |
| **Defect Escape Rate** | % of defects found in production vs. total defects | ≤ 2% | Per release |
| **Time-to-Fix (Critical)** | Days from defect logged to fixed & deployed | ≤ 1 day | Per defect |
| **Time-to-Fix (High)** | Days from defect logged to fixed & deployed | ≤ 3 days | Per defect |
| **Regression Pass Rate** | % of regression test cases passing | ≥ 95% | Per sprint |
| **Acceptance Sign-Off Time** | Days from feature dev complete to QA sign-off | ≤ 2 days | Per sprint |

---

## Quality Tools & Automation

### Recommended Test Automation Stack
- **Unit Testing:** Jest, Pytest, JUnit (framework-specific)
- **Integration Testing:** Postman, Insomnia, Cypress (API & UI)
- **End-to-End Testing:** Selenium, Cypress, Playwright
- **Performance Testing:** JMeter, k6, Lighthouse
- **Security Scanning:** SonarQube, Snyk, OWASP ZAP
- **Test Management:** TestRail, Zephyr, or GitHub Issues (lightweight)

### CI/CD Quality Gates
- [ ] All unit tests must pass (gate for merge)
- [ ] Security scan must pass (no high/critical vulnerabilities)
- [ ] Code coverage must not decrease (gate for merge)
- [ ] Linting/formatting must pass
- [ ] Integration tests run on develop branch (blocking for release)
- [ ] Performance regression detected (warning, not blocking)

---

## References
- `octoacme-execution-and-tracking.md` - Quality gates during execution
- `octoacme-release-and-deployment.md` - Pre-release quality verification
- `octoacme-roles-and-personas.md` - QA/Testing Lead role definition
- `octoacme-cross-functional-collaboration.md` - QA involvement in cross-functional meetings
