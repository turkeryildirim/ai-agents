# UI Pro — Prompt Examples

When invoking the `ui-pro` agent, include the following context for best results.

## 1. Component from Design
*Goal:* Build markup and styles from a design.
*Prompt Content:* `Build the [component] shown in [design reference]. Use our existing tokens and breakpoints from [file]. Produce semantic markup plus BEM SCSS, mobile-first. Include the layout-primitive justification, the responsive breakpoint table, and the accessibility report with measured contrast ratios.`

## 2. Tailwind → SCSS Conversion
*Goal:* Extract utilities into a maintainable stylesheet.
*Prompt Content:* `Convert this utility-first markup to semantic classes with custom SCSS: [paste]. Preserve the responsive behavior exactly, map values onto our existing token scale, and tell me explicitly what visual behavior changed (if anything).`

## 3. Accessibility Audit
*Goal:* Check a UI against WCAG AA.
*Prompt Content:* `Audit [component/page] for WCAG AA. Check semantic elements, heading hierarchy, label association, focus visibility, keyboard operability, ARIA correctness, reduced-motion support, contrast (state measured ratios), and touch target sizes. Give the fix for each failure.`

## 4. Responsive Layout
*Goal:* Build a layout that scales cleanly.
*Prompt Content:* `Build a responsive [layout type] for [content]. Mobile-first, using our breakpoints from [file]. Choose Grid or Flexbox per region and justify each. Use clamp() for fluid type and spacing. Show the breakpoint behavior table.`

## 5. SCSS Architecture Refactor
*Goal:* Fix a stylesheet that has become unmanageable.
*Prompt Content:* `Our stylesheet in [directory] has specificity problems and !important usage. Refactor it: migrate @import to @use, cap nesting at 3 levels, consolidate duplicate tokens into a single scale, and eliminate every !important. Report max specificity and nesting depth before and after.`
