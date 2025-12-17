# Automation Exercise E2E Testing with Playwright

This repository contains end-to-end (E2E) test scripts for [Automation Exercise](https://automationexercise.com/) 
Using [Playwright](https://playwright.dev/). The focus is on testing the website across:


- Desktop
- Tablet device
- Mobile device.


## Features:
- Written in **TypeScript**
- Runs on **Windows** environment
- Tests for **Desktop**, **Tablet**, and **Mobile** views
- Framework: **Visual Studio Code**
- Automated testing across different device dimensions using Playwright

---

## Getting Started

### Prerequisites
- **Node.js**: Install the latest version from [Node.js](https://nodejs.org/).
- **Visual Studio Code**: Install from [here](https://code.visualstudio.com/).
- Install Playwright:
   1. Open **Windows Command Prompt** or **PowerShell**
   2. Run:
      ```cmd
      npm install playwright
      ```

---

### Run Tests (Windows)
1. Clone the repository:
   ```cmd
   git clone https://github.com/samted42/test-automation-exercise.git
   ```

2. Navigate to the repository directory:
   ```cmd
   cd test-automation-exercise
   ```

3. Install dependencies:
   ```cmd
   npm install
   ```

4. Run Playwright tests:
   ```cmd
   npx playwright test
   ```

---

### Repository Structure
```plaintext
├── tests/
│   ├── desktop/
│   │   ├── test_homepage.spec.ts
│   │   ├── test_login.spec.ts
│   ├── mobile/
│   │   ├── test_cart.spec.ts
│   ├── tablet/
│       ├── test_products.spec.ts
├── playwright.config.ts
├── README.md
└── docs/
    ├── TestPlan.md
    ├── TestCases.md
```

---

### Playwright Config
The `playwright.config.ts` sets up device emulation for desktop, tablet, and mobile. You can find its configuration details in the file.

---

## Contribution
Feel free to create pull requests or raise issues to improve tests and usability.

## License
MIT License
