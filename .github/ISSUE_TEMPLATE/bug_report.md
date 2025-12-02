---
name: Bug Report
about: Create a report to help us improve
title: "[Bug] - "
labels: bug
assignees:


body:
  - type: markdown
    attributes:
      value: | # Use the new repository name in the header
        ## Bug Report for `ContextLens-AI-Powered-Web-Summarizer-Browser-Extension`

        Thank you for taking the time to report a bug! Please provide as much detail as possible to help us quickly understand and resolve the issue. This report will be processed by the Apex Technical Authority agents for rapid triage and resolution.

        --- # Separator adhering to Apex standards

  - type: input
    id: summary
    attributes:
      label: Concise Summary of the Bug
      description: A brief, clear description of the bug.
      placeholder: e.g., Extension crashes when summarizing long Reddit threads.
    validations:
      required: true
  - type: input
    id: steps
    attributes:
      label: Steps to Reproduce
      description: Provide a step-by-step guide to reproduce the bug.
      placeholder: |
        1. Go to a specific website (URL if possible).
        2. Perform action X.
        3. Observe the unexpected behavior.
    validations:
      required: true
  - type: textarea
    id: expected_behavior
    attributes:
      label: Expected Behavior
      description: What you expected to happen.
      placeholder: e.g., The extension should provide a concise summary of the article.
    validations:
      required: true
  - type: textarea
    id: actual_behavior
    attributes:
      label: Actual Behavior
      description: What actually happened, including any error messages.
      placeholder: e.g., The extension showed an error message 'API rate limit exceeded' and no summary was generated.
    validations:
      required: true
  - type: input
    id: environment
    attributes:
      label: Environment Details
      description: Specify your operating system, browser version, and extension version.
      placeholder: e.g., Windows 11, Chrome 120.0.6099.217, Extension v1.2.0
    validations:
      required: true
  - type: textarea
    id: additional_context
    attributes:
      label: Additional Information (Optional)
      description: Any other context, screenshots, or logs that might be helpful.
      placeholder: You can paste screenshots or relevant log snippets here.
    validations:
      required: false
  - type: markdown
    attributes:
      value: | # Dynamic links to repository and documentation
        --- # Separator adhering to Apex standards

        **Repository:** [chirag127/ContextLens-AI-Powered-Web-Summarizer-Browser-Extension](https://github.com/chirag127/ContextLens-AI-Powered-Web-Summarizer-Browser-Extension)
        **AI Agent Directives:** [AGENTS.md](https://github.com/chirag127/ContextLens-AI-Powered-Web-Summarizer-Browser-Extension/blob/main/AGENTS.md)

        *This report will be auto-processed by the Apex Technical Authority's AI agents.*