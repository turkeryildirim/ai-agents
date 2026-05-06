# UI/UX — Prompt Examples

When invoking the `ui-ux` agent, include the following context for best results.

## 1. New Component SCSS
*Goal:* Write SCSS for a new UI component.
*Prompt Content:* `Write BEM SCSS for a [product card / user profile / modal dialog] component. Design requirements: [list visual specs — colors, spacing, border-radius]. The project uses these SCSS variables: [$primary: #..., $spacing-base: 8px, breakpoints: mobile 768px, tablet 1024px]. Mobile-first approach.`

## 2. Tailwind to SCSS Conversion
*Goal:* Convert messy Tailwind markup into clean SCSS.
*Prompt Content:* `Convert this Tailwind component to semantic HTML + custom SCSS using BEM methodology: [paste Tailwind HTML]. Extract all utility classes into meaningful class names. Use the project's existing variables ($primary, $font-size-base). Remove all Tailwind dependencies from this component.`

## 3. Accessibility Audit
*Goal:* Review a component for WCAG compliance.
*Prompt Content:* `Review this [form / navigation / modal / data table] HTML for WCAG 2.1 AA compliance: [paste HTML]. Check: proper label associations, aria-* attributes, keyboard navigation (tabindex, focus management), color contrast (provide specific hex values to check), and screen reader announcements for dynamic content.`

## 4. Responsive Layout
*Goal:* Create a responsive grid layout.
*Prompt Content:* `Create a responsive [product grid / dashboard layout / card list] using CSS Grid / Flexbox. Requirements: [X columns on desktop, Y on tablet, single column mobile]. Items have [min/max width constraints]. Implement with custom SCSS using the project's breakpoint variables: [$breakpoint-md: 768px, $breakpoint-lg: 1200px].`

## 5. Animation & Interaction
*Goal:* Add smooth transitions or animations.
*Prompt Content:* `Add CSS transitions/animations to the [dropdown menu / modal / toast notification / accordion] component in [file path]. Requirements: [smooth open/close, respect prefers-reduced-motion, GPU-accelerated where possible]. Provide the SCSS and any necessary JS class toggle changes.`
