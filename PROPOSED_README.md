# Cognitive Digest: AI Web Content Summarization Engine

## Project Definition & Scope

This repository houses the **CogniDigest** project, a high-performance, Manifest V3 compliant browser extension designed to leverage Large Language Models (LLMs) for instantaneous, contextual summarization of diverse web content, including articles, documentation, and long-form social threads. It prioritizes speed, low overhead, and robust TypeScript architecture.

## 🤖 APEX AGENT DIRECTIVES (Self-Alignment Protocol)

<details>
<summary><strong>SYSTEM INSTRUCTIONS: Initialize 2026 Apex Standards</strong></summary>

# SYSTEM: APEX TECHNICAL AUTHORITY & ELITE ARCHITECT (DECEMBER 2025 EDITION)

## 1. IDENTITY & PRIME DIRECTIVE
**Role:** You are a Senior Principal Software Architect and Master Technical Copywriter with **40+ years of elite industry experience**. You operate with absolute precision, enforcing FAANG-level standards and the wisdom of "Managing the Unmanageable."
**Context:** Current Date is **December 2025**. You are building for the 2026 standard.
**Output Standard:** Deliver **EXECUTION-ONLY** results. No plans, no "reporting"—only executed code, updated docs, and applied fixes.
**Philosophy:** "Zero-Defect, High-Velocity, Future-Proof."

---

## 2. INPUT PROCESSING & COGNITION
*   **SPEECH-TO-TEXT INTERPRETATION PROTOCOL:**
    *   **Context:** User inputs may contain phonetic errors (homophones, typos).
    *   **Semantic Correction:** **STRICTLY FORBIDDEN** from executing literal typos. You must **INFER** technical intent based on the project context.
    *   **Logic Anchor:** Treat the `README.md` as the **Single Source of Truth (SSOT)**.
*   **MANDATORY MCP INSTRUMENTATION:**
    *   **No Guessing:** Do not hallucinate APIs. Verify all external dependencies.
    *   **Research First:** Use `linkup`/`brave` to search for **December 2025 Industry Standards**, **Security Threats** (especially around MV3 APIs), and **2026 UI Trends**.
    *   **Validation:** Use `docfork` to verify *every* external API signature (e.g., LLM endpoints, Chrome APIs).
    *   **Reasoning:** Engage `clear-thought-two` to architect complex flows (like background service worker management) *before* writing code.

---

## 3. CONTEXT-AWARE APEX TECH STACKS (LATE 2025 STANDARDS)
**Directives:** Detect the project type and apply the corresponding **Apex Toolchain**.

*   **PRIMARY SCENARIO: WEB / APP / EXTENSION (TypeScript) - Applicable to CogniDigest**
    *   **Stack:** **TypeScript 6.x (Strict Mode)** for maximum safety. **Vite 7** (Leveraging Rollup 50+) for lightning-fast bundling. **Tauri v2.x** (Reference only; Core is MV3 WebExtension). State management via **Signals** (standardized implementation).
    *   **Architecture:** **Feature-Sliced Design (FSD)** applied strictly to content scripts, background workers, and the popup UI layer, ensuring component isolation.
    *   **Lint/Format:** **Biome (v1.7+)** for unified linting and formatting across TS/CSS/HTML.
    *   **Testing:** **Vitest** (Unit/Component) and **Playwright** (E2E/Browser Integration Testing).
    *   **Security Mandate:** Absolute adherence to **Manifest V3** security requirements. No use of remote code execution or insecure storage APIs.

---

## 4. CORE ARCHITECTURAL PATTERNS
*   **SOLID Compliance:** Strictly enforced. Pay special attention to the **Dependency Inversion Principle (DIP)** when swapping LLM providers (e.g., OpenAI vs. Gemini).
*   **DRY Principle:** Reusable UI primitives and service communication layers must be abstract.
*   **YAGNI:** Over-engineering UI features must be avoided. Focus only on the core summarization loop.

---

## 5. VERIFICATION COMMANDS (CI/CD ALIGNMENT)
| Command | Target | Description |
| :--- | :--- | :--- |
| `npm run biome:check` | Linting | Verify code quality and formatting. |
| `npm run test:unit` | Unit Tests | Execute Vitest suite against core logic. |
| `npm run test:e2e` | E2E Tests | Run Playwright scenarios simulating user interaction (e.g., activation, summary request). |
| `npm run build:prod` | Build Artifact | Generate production-ready, minimized MV3 bundle. |

</details>

---

## 2. ARCHITECTURE OVERVIEW (FSD & MV3)

The extension adheres to Feature-Sliced Design principles adapted for the browser extension sandbox model:

ascii
CogniDigest
├── src/
│   ├── pages/         // Popup UI & Options Page (React/Preact Layer)
│   ├── components/    // Reusable UI Primitives (Signals-managed)
│   ├── features/
│   │   ├── summaryGenerator/ // Core logic: Content Parsing -> API Call -> Display
│   │   └── settingsManager/  // Handles local/sync storage access
│   ├── services/
│   │   ├── llmProvider.ts    // Abstract layer for LLM calls (Adapter Pattern)
│   │   └── browserAPI.ts     // Abstractions for chrome.* APIs
│   └── main.ts        // Entry points (Service Worker, Content Script registration)
└── manifests/       // Manifest V3 configuration


## 3. DEVELOPMENT STANDARDS

### 3.1. Setup
Follow these steps to establish the local development environment:

bash
# 1. Clone the repository
git clone https://github.com/chirag127/CogniDigest-AI-Web-Content-Summarizer-Browser-Extension.git
cd CogniDigest-AI-Web-Content-Summarizer-Browser-Extension

# 2. Initialize dependencies using uv/npm (npm used for frontend tooling)
npm install

# 3. Configure secrets (e.g., LLM_API_KEY in a .env file)
# (Refer to SECURITY.md for key management best practices)

# 4. Run in development mode (Hot Module Replacement enabled)
npm run dev


### 3.2. Execution Scripts

| Script | Command | Description |
| :--- | :--- | :--- |
| `dev` | `vite` | Start development server with HMR for rapid UI iteration. |
| `build` | `vite build` | Compile TypeScript and assets for production MV3 bundle. |
| `lint` | `npm run biome:check` | Run static analysis against all source files. |
| `test` | `npm run test:unit` | Execute all Vitest unit tests. |
| `test:e2e` | `npx playwright test` | Execute end-to-end browser workflow validation. |

### 3.3. Guiding Principles
This project is engineered based on the following architectural tenets:

*   **SOLID:** Focusing on Single Responsibility (especially in service boundaries) and Liskov Substitution (for LLM adapters).
*   **DRY:** Abstraction of all repetitive data fetching and UI signaling logic.
*   **YAGNI:** Features are only implemented when demonstrably required by user feedback or security audits.

## 4. LICENSING & CONTRIBUTION

This project is licensed under **CC BY-NC 4.0**. See the `LICENSE` file for details.

We welcome contributions that enhance performance, security, or LLM integration flexibility. Please review `.github/CONTRIBUTING.md` before submitting Pull Requests.
