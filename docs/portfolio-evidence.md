# Portfolio evidence

This repository is intended for employers, headhunters and technical interviewers who need credible evidence of software-engineering work without public disclosure of proprietary source code.

## What this project demonstrates

| Competency | Evidence |
|---|---|
| Office/VSTO engineering | PowerPoint COM add-in hosted through VSTO with a custom task pane. |
| Product architecture | Clear separation between host bootstrap, task-pane UI, service integration, configuration, verification and session state. |
| AI integration | Azure OpenAI and OpenAI Direct support across text, image, vision and chart/diagram generation use cases. |
| Secure configuration | DPAPI-encrypted per-user settings and no secrets embedded in code or installer. |
| Robust provider UX | Deployment/model discovery, filtering and verification before selection. |
| State management | Per-presentation session isolation for chat and image history. |
| Deployment thinking | ClickOnce-first packaging with optional Inno Setup bootstrapper. |
| Documentation quality | Architecture, workflows, deployment and security boundaries documented without exposing source code. |

## Suggested discussion topics for interviews

- Why a centralized integration facade is safer than calling provider APIs directly from UI controls.
- How to handle Azure API-version changes without breaking the configuration dialog.
- How per-presentation state reduces UX surprises in Office add-ins.
- How to design a public portfolio repository when the production code is proprietary.
- How to balance usability, security and maintainability in an AI-enabled desktop application.

## Publication boundary

The public repository is intentionally designed as an **evidence layer**, not as an open-source release. It provides enough information for technical evaluation while protecting the proprietary source code and implementation-sensitive business value.
