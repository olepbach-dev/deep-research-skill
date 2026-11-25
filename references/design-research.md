# Design research

Design research should turn product and user evidence into a testable design contract—not a collection of fashionable adjectives.

## Inputs

- Product goal and user job
- Existing brand/design system
- Current interface and analytics
- Customer interviews, support logs, or market-language evidence
- Relevant platform guidelines and accessibility standards
- Reference products with direct links/screenshots

## Analyze

- Information hierarchy and primary action
- End-to-end user journey
- Empty, loading, error, success, destructive, and permission states
- Responsive behavior
- Keyboard, focus, contrast, semantics, and reduced-motion needs
- Reusable patterns from the existing codebase/design system
- Reference patterns: what is observed versus what is merely preferred

## Deliverable

A useful design contract contains:

- Goal, user, constraints, and assumptions
- Journey and screen/state inventory
- Layout and component behavior
- Tokens tied to an existing brand or an explicit rationale
- Interaction and motion rules, including reduced motion
- Accessibility acceptance criteria
- Responsive rules
- Visual QA plan with target viewport(s) and reference screenshots
- Open decisions

Do not invent exact colors, spacing, or animations solely to make a document appear "premium." If brand evidence is absent, label tokens as proposals.

For implementation work, verify rendered output against the contract at representative desktop/mobile sizes and review real screenshots rather than trusting code alone.

