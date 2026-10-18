# Task #4: Few-Shot and Role Assignment

## Experiment B: Role Assignment

### Objective
To explore how assigning a specialized role influences an AI's analysis and recommendations.

### Prompt Used
Act as a frontend accessibility reviewer specializing in accessible and responsive tourism websites.

Examine my existing LakbayMarinduque interface, particularly:
- HTML semantics and heading structure
- Keyboard navigation and visible focus indicators
- Navigation links and mobile menu accessibility
- Labels and accessibility of destination category filters
- Image alternative text, if images are used
- Text readability, color contrast, and responsive layout

Identify specific accessibility or usability problems in the existing implementation. For each issue:
1. Identify the relevant element or file, if possible.
2. Explain why it may be a problem.
3. Recommend a targeted improvement.

Constraints:
- Review the existing code before making recommendations.
- Do not change or overwrite any project files.
- Do not invent problems that you cannot identify in the code.
- Distinguish confirmed issues from items that need browser or accessibility testing.
- Keep the recommendations practical and within the current LakbayMarinduque project scope.

Return a concise review with findings and recommended improvements.

### Actual Copilot Response
Copilot reviewed the HTML, CSS, and JavaScript in `outputs/structured/`.

**Confirmed findings in the code:**
1. The Poctoy White Beach and Mount Malindig cards have “Learn more” links that both lead to `#plan`, a general planning section rather than destination-specific information.
2. Several captions, labels, filter buttons, and footer text use small font sizes, ranging from approximately 6px to 11px.

**Items requiring further verification:**
3. The focus outline on destination cards may be clipped because the parent card uses `overflow: hidden`.
4. The `aria-live="polite"` destination list may result in verbose or unclear announcements when filters change.
5. Text contrast over gradients, horizontal overflow, and content visibility require visual testing at desktop and mobile widths.

**Positive findings:**
- The page uses semantic landmarks and a main heading with a heading hierarchy.
- A skip link is present.
- Native buttons use `aria-expanded` and `aria-pressed` states.
- The menu script updates its expanded state, closes when a link is selected, and supports Escape.
- No `<img>` elements are missing alternative text. CSS artwork is marked decorative with `aria-hidden` and described as illustrative in visible text.

Copilot stated that this was a code-only review. It did not perform browser, contrast-tool, or screen-reader testing and did not make project changes.

### Output File
`outputs/role-assignment-review.md`

### Observation
Assigning Copilot the role of a frontend accessibility reviewer encouraged it to focus on accessibility and usability rather than visual design alone. It identified code-based issues, suggested practical improvements, and separated findings that require further testing from issues visible in the source code.

### Testing Status
Code review completed. Browser testing, screen-reader testing, and contrast verification have not yet been performed.