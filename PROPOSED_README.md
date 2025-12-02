# ContextLens-AI-Powered-Web-Summarizer-Browser-Extension

![Apex Authority Banner](https://img.shields.io/badge/APEX%20ARCHITECT%20v1.0-Elite%20Standard-blue)

[![Build Status](https://img.shields.io/github/actions/workflow/status/chirag127/ContextLens-AI-Powered-Web-Summarizer-Browser-Extension/ci.yml?style=flat-square&label=Build)](https://github.com/chirag127/ContextLens-AI-Powered-Web-Summarizer-Browser-Extension/actions/workflows/ci.yml)
[![Code Coverage](https://img.shields.io/codecov/c/github/chirag127/ContextLens-AI-Powered-Web-Summarizer-Browser-Extension?style=flat-square)](https://codecov.io/gh/chirag127/ContextLens-AI-Powered-Web-Summarizer-Browser-Extension)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-orange?style=flat-square)](https://github.com/chirag127/ContextLens-AI-Powered-Web-Summarizer-Browser-Extension/blob/main/LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/chirag127/ContextLens-AI-Powered-Web-Summarizer-Browser-Extension?style=flat-square)](https://github.com/chirag127/ContextLens-AI-Powered-Web-Summarizer-Browser-Extension)

[⭐ Star this Repo ⭐](https://github.com/chirag127/ContextLens-AI-Powered-Web-Summarizer-Browser-Extension)

---

**BLUF:** ContextLens delivers real-time, on-demand summaries of complex web content—articles, forums, and documents—directly within your browser using cutting-edge multimodal LLMs. It aggressively reduces information overload by distilling insights instantly.

## Architecture Overview

This project adheres to a strict **Micro-Frontend/Background Service** architecture suitable for Manifest V3 extensions, ensuring optimal performance and isolation between the UI (Content Script) and the AI Processing Layer (Background Service Worker).

mermaid
graph TD
    A[User Interaction: Scroll/Click] --> B(Content Script: DOM Capture)
    B --> C{Service Worker: Manifest V3 Boundary}
    C --> D[API Handler: Secure Storage/Config]
    D --> E(Gemini/LLM API Gateway)
    E --> F[AI Response Processing]
    F --> C
    C --> G[Content Script: Injection & Display]
    G --> A

    subgraph Frontend (Browser Extension)
        A
        B
        G
    end

    subgraph Backend (Service Worker)
        C
        D
    end

    style E fill:#f9f,stroke:#333,stroke-width:2px


## Table of Contents

1.  [Architecture Overview](#architecture-overview)
2.  [Agent Directives](#-ai-agent-directives)
3.  [Development Standards](#development-standards)
4.  [Technology Stack](#technology-stack)

---

## 🤖 AI Agent Directives

<details>
<summary>🔬 Apex Cognitive Alignment & Verification Protocols (December 2025)</summary>

**CONTEXT:** This project is a high-performance, user-facing **Browser Extension (JavaScript/TypeScript, Manifest V3)** designed for real-time cognitive offloading via external LLMs (specifically **Google Gemini API**).

### 1. Technology Stack Definition
*   **Core Language:** TypeScript 5.x (Strict Mode enforced via `tsconfig.json`).
*   **Runtime Environment:** Browser Environment (V8 engine for Content Scripts/Service Workers).
*   **Packaging:** Manifest V3 compliant build process (e.g., using WXT or custom Vite configuration).
*   **API Dependency:** Google Gemini API (Use `gemini-2.5-pro` or newer as the default model path).
*   **State Management:** Minimalist approach; rely on `chrome.storage.local` for persistent data and message passing (`chrome.runtime.sendMessage`) for in-memory communication.

### 2. Architectural Patterns & Enforcement
*   **SOLID Compliance:** Mandatory application of the **Single Responsibility Principle (SRP)**. Content scripts handle DOM manipulation ONLY; Service Workers handle API orchestration and business logic ONLY.
*   **DRY Principle:** All API request boilerplate (headers, error parsing) must be abstracted into dedicated utility modules (`/src/api/handler.ts`).
*   **Security (Crucial):** NO API keys or secrets are to be hardcoded. All keys must be fetched securely through the Service Worker, validated against environment variables loaded during the build process, or dynamically injected via secure browser APIs.
*   **Performance:** Content scripts must execute asynchronously to avoid main thread blocking. UI updates must be debounced/throttled during scrolling events.

### 3. Verification Commands (LINT & BUILD)
All development operations must begin with system alignment validation:

1.  **Dependency Resolution (uv/npm equivalent):** `npm install`
2.  **Lint & Format Check (Biome/Ruff equivalent):** `npm run lint:check`
3.  **Full Build & Bundle Verification:** `npm run build`
4.  **Local Testing (Vitest/Playwright):** `npm run test:unit`

**Post-Modification Mandate:** Any change touching the API layer or DOM interaction logic requires a corresponding E2E test update using Playwright against a staged environment or mock service worker implementation.

</details>

## Development Standards

### Prerequisites
Ensure Node.js (v20+) and npm/yarn are installed.

### Setup
bash
git clone https://github.com/chirag127/ContextLens-AI-Powered-Web-Summarizer-Browser-Extension.git
cd ContextLens-AI-Powered-Web-Summarizer-Browser-Extension
npm install
# Ensure GEMINI_API_KEY is set in your environment or .env file


### Scripts
| Command | Description | Standard | 
| :--- | :--- | :--- |
| `npm run build` | Compiles TypeScript and bundles for production deployment. | High Velocity |
| `npm run dev` | Runs the development build watcher with hot-reloading emulation. | Rapid Iteration |
| `npm run lint:check` | Checks code quality using Biome/Ruff standards. | Zero Defect |
| `npm run test:unit` | Executes Vitest suite for module logic. | Verification |
| `npm run test:e2e` | Executes Playwright tests for full user flows. | Future Proofing |

### Core Principles
*   **SOLID:** Maintain clear separation of concerns, especially between UI and logic layers.
*   **DRY:** Eliminate boilerplate code, centralize API interactions.
*   **YAGNI:** Implement features only when explicitly required by user stories; avoid premature optimization.

## Technology Stack

This repository is engineered for modern browser extension deployment using a strict TypeScript pipeline.

*   **Language:** TypeScript (Strict Mode)
*   **Build Tool:** Vite / Custom Web Extension Builder
*   **Linter/Formatter:** Biome (for speed and standardization)
*   **Testing:** Vitest (Unit), Playwright (E2E)
*   **AI Backend:** Google Gemini API (Leveraging `gemini-2.5-pro`)
*   **Manifest:** Manifest Version 3
*   **Styling:** (TBD based on initial scaffolding, assumed modern CSS-in-JS or plain CSS/SCSS)

---

## License

This project is licensed under the Creative Commons Attribution-NonCommercial 4.0 International License. See the [LICENSE](https://github.com/chirag127/ContextLens-AI-Powered-Web-Summarizer-Browser-Extension/blob/main/LICENSE) file for details.