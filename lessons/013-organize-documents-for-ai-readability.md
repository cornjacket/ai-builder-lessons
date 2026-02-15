# 013 - Organize Documents for AI Readability

## Context

When collaborating with AI agents on software development, the way documentation is structured significantly impacts the AI's ability to efficiently find, process, and apply information. Large, monolithic documents, while convenient for human authors, can become problematic for AI agents due to context window limitations and the "lost in the middle" phenomenon, where important details are overlooked within extensive text blocks.

## Decision

To optimize documentation for AI readability and processing efficiency, adopt a structured, hierarchical approach where large documents or sections are refactored into index documents that point to smaller, more focused child documents.

## Guidelines

1.  **Index-Based Organization:** For any document or section that grows beyond a manageable size (e.g., several screen lengths, or covering multiple distinct topics), convert it into an index document. This index should contain:
    *   A brief summary of the overall topic.
    *   Short, concise summaries or introductions for each sub-topic or section.
    *   Clear, clickable links (e.g., Markdown links) to separate child documents that contain the full details for each sub-topic.

2.  **Child Documents in Subfolders:** Store these detailed child documents in dedicated subfolders. This maintains a clean file structure and logical grouping.

3.  **Proactive Refactoring:** As a document grows, or as a single section within a document becomes overly detailed, identify opportunities to refactor it:
    *   **Document becomes too large:** Turn the entire document into an index (`README.md` is often suitable for this role within a directory). Move its original content into several child files, linked from the new index.
    *   **Section becomes too detailed:** Extract the content of that section into a new child document. Replace the original section with a summary and a link to the new child document.

4.  **Benefits for AI Agents:**
    *   **Efficient Context Management:** AI agents can first read the concise index document. This allows them to quickly grasp the overall scope and identify only the most relevant child documents to load into their processing context. This avoids wasting context tokens on irrelevant information.
    *   **Improved Focus and Recall:** By working with smaller, topic-specific documents, the AI agent can maintain better focus on the task at hand, improving information recall and reducing the likelihood of overlooking critical details buried in large text blocks.
    *   **Enhanced Navigation:** The linked structure facilitates programmatic navigation, allowing the AI to traverse related concepts efficiently without exhaustive searches through single, giant files.
    *   **Scalability and Maintainability:** This structure makes the documentation easier to maintain and scale as the project evolves, benefiting both human and AI collaborators.

## Example

Instead of:
```markdown
# Design Specification

## Section A: Overview
... (very long text) ...

## Section B: Detailed Component X
... (very long text) ...
```

Consider:
```markdown
# Design Specification (Index)

This document provides an overview of the design.

## Section A: Overview

A brief summary of Section A.
[Read more about Section A](section-a/README.md)

## Section B: Detailed Component X

A brief summary of Component X.
[Read more about Component X](component-x/details.md)
```