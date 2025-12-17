# Test Plan for Automation Exercise Website

## Project Objective:
To automate the End-to-End (E2E) testing of the [Automation Exercise Website](https://automationexercise.com/). 
Ensure compatibility across Desktop, Tablet, and Mobile devices using Playwright.

---

## In Scope:
- **Included Tests:**
  - Homepage navigation
  - Signup and Login workflows
  - Product search & cart functionality
  - Responsive design validation
 
## Out of Scope:
- **Excludeed Tests:**
  - Non-functional requirements (e.g., performance, security)

---

## Test Strategy:

### Tools and Frameworks:
- **Playwright** for browser automation.
- Test runners: Use Playwright’s built-in test runner with TypeScript.

### Environments:
- **Browser**: Chrome, Firefox, WebKit
- **OS**: Windows
- Test three devices:
  - Desktop: **1366x768**
  - Tablet: **768x1024**
  - Mobile: **375x667**

### Entry/Exit Criteria:
| Criteria        | Description                     |
|-----------------|--------------------------------|
| **Entry**       | Website is accessible. Setup is complete. |
| **Exit**        | All priority-1 bugs are fixed. Test scenarios executed. |

---

## Roles and Responsibilities:
| Role             | Responsibility              |
|------------------|-----------------------------|
| Test Analyst     | Create test scripts and report results |
| Developer        | Debug and resolve issues |
| Project Manager  | Approve the final testing phase and production rollout |

---

### Risks and Contingencies
| Risk             | Mitigation Plan                 |
|------------------|----------------------------------|
| UI changes       | Maintain robust selectors       |
| Device incompatibility | Use Playwright’s viewport profiles |

---

## Deliverables:
- Test cases (TestCases.md)
- Test scripts in the repository
- Test execution report
