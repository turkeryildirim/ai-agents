# SwiftUI Pro — Prompt Examples

When invoking the `swiftui-pro` agent, include the following context for best results.

## 1. New Screen
*Goal:* Build a screen with correct data flow.
*Prompt Content:* `Build the [screen] in SwiftUI. Deployment target iOS [n], Swift [version], strict concurrency [level]. Use @Observable for the model, extracted subviews, and .task(id:) for loading. Include the data flow table, the accessibility checklist with measured contrast, and a fallback for any version-gated API. Do not write tests — list behaviors for swiftui-tester.`

## 2. Strict Concurrency Migration
*Goal:* Fix isolation instead of silencing it.
*Prompt Content:* `Enabling strict concurrency produces these warnings: [paste]. Fix the actor isolation properly — do NOT use @unchecked Sendable to silence anything. Show the isolation table with before/after per file and explain which types genuinely need to cross actor boundaries.`

## 3. @Observable Migration
*Goal:* Move off ObservableObject.
*Prompt Content:* `Migrate [models] from ObservableObject to @Observable. Update the property wrappers at every call site (@StateObject → @State, @ObservedObject → let/@Bindable), and tell me where the invalidation scope narrows as a result. Our target is iOS [n].`

## 4. Rendering Performance
*Goal:* Stop unnecessary re-renders.
*Prompt Content:* `The [view] stutters when [interaction]: [files]. Use Self._printChanges() reasoning to identify what triggers re-renders, extract subviews to narrow invalidation, check lazy container identity stability, and give before/after code.`

## 5. SwiftData Model Review
*Goal:* Audit models before they ship.
*Prompt Content:* `Review the SwiftData models in [files]. Check relationship delete rules, predicate safety, @Query usage, indexing on filtered/sorted properties, and migration safety for the change in [description]. Report findings by file with rule ids.`
