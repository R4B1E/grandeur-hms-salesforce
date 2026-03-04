# Grandeur HMS — Salesforce Implementation Guide

A comprehensive Salesforce implementation for **Grandeur Hotel Management System (HMS)** — covering data modelling, security, automation, and a guest self-service portal, all built natively on the Salesforce platform.

---

## Table of Contents

1. [Project Description](#project-description)
2. [Guide Documents](#guide-documents)
3. [Prerequisites](#prerequisites)
4. [Quick Start Summary](#quick-start-summary)
5. [Repository Structure](#repository-structure)
6. [Contributing](#contributing)
7. [License](#license)

---

## Project Description

Grandeur HMS is a full-featured Hotel Management System built entirely on the Salesforce platform. It leverages Salesforce's CRM, automation, and community capabilities to manage the complete hotel guest lifecycle — from reservation and check-in through billing, housekeeping, and post-stay engagement. The implementation is designed to be scalable, maintainable, and fully aligned with Salesforce best practices.

---

## Guide Documents

| Document | Description |
|---|---|
| [Implementation Guide](docs/implementation-guide.md) | End-to-end setup and deployment instructions |
| [Data Model](docs/data-model.md) | Custom objects, fields, and relationships |
| [Security Model](docs/security-model.md) | Profiles, permission sets, sharing rules, and OWD settings |
| [Automation Guide](docs/automation-guide.md) | Flows, Apex triggers, and process automation |
| [Guest Portal Guide](docs/guest-portal-guide.md) | Experience Cloud setup for the guest self-service portal |

---

## Prerequisites

### Salesforce Editions

- **Enterprise Edition** or **Unlimited Edition** (required for advanced automation and Experience Cloud)

### Required Licenses

| License | Purpose |
|---|---|
| **Sales Cloud** | Account, Contact, and Opportunity management for corporate clients |
| **Service Cloud** | Case management for guest requests and complaints |
| **Experience Cloud** | Guest self-service portal |

### Tools

| Tool | Version | Notes |
|---|---|---|
| [Salesforce CLI (`sf`)](https://developer.salesforce.com/tools/salesforcecli) | Latest | Used for org authentication, metadata deployment, and scripting |
| [Visual Studio Code](https://code.visualstudio.com/) | Latest | Recommended IDE |
| [Salesforce Extension Pack](https://marketplace.visualstudio.com/items?itemName=salesforce.salesforcedx-vscode) | Latest | VS Code extensions for Apex, LWC, and org management |
| Git | 2.x+ | Source control |

---

## Quick Start Summary

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-org/grandeur-hms-salesforce.git
   cd grandeur-hms-salesforce
   ```

2. **Authenticate to your target org**
   ```bash
   sf org login web --alias grandeur-hms
   ```

3. **Deploy metadata to the org**
   ```bash
   sf project deploy start --target-org grandeur-hms
   ```

4. **Assign permission sets to users**
   ```bash
   sf org assign permset --name GrandeurHMS_Admin --target-org grandeur-hms
   ```

5. **Load sample / seed data** *(optional)*
   ```bash
   sf data import tree --files data/sample-data-plan.json --target-org grandeur-hms
   ```

6. **Activate and configure the Guest Portal**
   Follow the steps in [docs/guest-portal-guide.md](docs/guest-portal-guide.md).

7. **Review automation**
   Confirm all Flows and Apex triggers are active as described in [docs/automation-guide.md](docs/automation-guide.md).

---

## Repository Structure

```
grandeur-hms-salesforce/
├── docs/
│   ├── implementation-guide.md   # Full deployment and setup guide
│   ├── data-model.md             # Object schema and ERD
│   ├── security-model.md         # Profiles, permission sets, sharing
│   ├── automation-guide.md       # Flows, triggers, scheduled jobs
│   └── guest-portal-guide.md     # Experience Cloud / portal setup
├── force-app/
│   └── main/
│       └── default/
│           ├── classes/          # Apex classes and test classes
│           ├── flows/            # Salesforce Flows (XML)
│           ├── lwc/              # Lightning Web Components
│           ├── objects/          # Custom object and field metadata
│           ├── permissionsets/   # Permission set metadata
│           ├── profiles/         # Profile metadata
│           └── triggers/         # Apex triggers
├── data/
│   └── sample-data-plan.json     # Seed data for development orgs
├── scripts/
│   └── deploy.sh                 # Helper deployment script
├── .forceignore                  # Files excluded from deployment
├── sfdx-project.json             # Salesforce DX project configuration
└── README.md                     # This file
```

---

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository and create a feature branch (`git checkout -b feature/your-feature`).
2. Make your changes and ensure all Apex tests pass (`sf apex run test --target-org grandeur-hms --result-format human`).
3. Commit your changes with a clear message and open a Pull Request against `main`.
4. Ensure your PR description references any related issues and includes testing steps.

Please review the [Implementation Guide](docs/implementation-guide.md) before contributing to understand the project conventions and standards.

---

## License

This project is licensed under the [MIT License](LICENSE).  
© Grandeur HMS. All rights reserved.