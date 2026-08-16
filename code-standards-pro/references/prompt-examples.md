# Code Standards Pro — Prompt Examples

When invoking the `code-standards-pro` agent, include the following context for best results.

## 1. God Class Breakup
*Goal:* Split an oversized class along responsibility lines.
*Prompt Content:* `Review [file]. Produce a Responsibility Map, then propose the smallest set of extractions that gives each unit a one-sentence responsibility. Show before/after code for each extraction and order them by payoff vs. risk.`

## 2. Premature Abstraction Check
*Goal:* Decide whether an abstraction earns its keep.
*Prompt Content:* `Is the abstraction in [file] justified? Count the real call sites, judge it against YAGNI, and tell me whether to keep, inline, or generalize it. Cite rule ids.`

## 3. Function Signature Redesign
*Goal:* Clean up a bloated signature.
*Prompt Content:* `The function [name] in [file] takes [n] parameters including boolean flags. Redesign the signature — remove flag arguments, introduce a parameter object or split the function. Show before/after.`

## 4. Testability Audit
*Goal:* Find the seams before writing tests.
*Prompt Content:* `This code is hard to test: [file]. Identify every hard dependency, name the injection points that would make it testable, and list the observable behaviors worth asserting. Do not write the tests — hand them to the tester agent.`

## 5. Complexity Report
*Goal:* Get numbers instead of opinions.
*Prompt Content:* `Produce a complexity report for [directory]: lines, branch count, nesting depth, and parameter count per function. Flag anything above [threshold] with a concrete simplification and cite the rule id.`
