# Directives (Layer 1 - The Brain)

This folder contains **Standard Operating Procedures (SOPs)** that define goals, tools, and edge cases for each task.

## Purpose
- Define **what** needs to be done and **how**
- Specify tools and APIs required
- Document edge cases and error handling strategies
- Serve as the source of truth for all automation logic

## Structure
Each directive should be a markdown file with:
- **Goal**: What the task accomplishes
- **Prerequisites**: Required credentials, data, or state
- **Steps**: Ordered execution steps
- **Tools**: List of tools/APIs used
- **Edge Cases**: Known failure modes and how to handle them
- **Success Criteria**: How to verify completion

## Naming Convention
`{domain}_{action}.md` — e.g., `turo_email_classification.md`, `turo_reservation_sync.md`
