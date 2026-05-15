# SwiftUI Reviewer — Prompt Examples

When invoking the `swiftui-reviewer` agent, include the following context for best results.

## 1. Post-Feature Review

*Goal:* Review code written for a new SwiftUI screen.
*Prompt Content:* `Review the recently written code in [file paths]. This is a [screen / component / ViewModel] that [brief description]. Pay special attention to [state management / async loading / navigation]. The project targets iOS [version] and uses [MVVM / TCA / MV pattern].`

## 2. State Management Audit

*Goal:* Verify property wrapper usage is correct after a refactor.
*Prompt Content:* `Audit the state management in [file path]. We migrated from ObservableObject to @Observable. Verify: all @Published annotations are removed, @StateObject usages are replaced with @State or direct var, @ObservedObject dependencies are using @Bindable where needed, and no @Observable class is mutated off @MainActor.`

## 3. Concurrency / @MainActor Review

*Goal:* Verify Swift Concurrency isolation after adding async loading.
*Prompt Content:* `Perform a concurrency-focused review of [file path]. We just converted onAppear + DispatchQueue.main.async to .task {} with @MainActor. Verify: the ViewModel is @MainActor annotated, .task {} is used instead of onAppear, no DispatchQueue calls remain, and Task.detached is not used unnecessarily.`

## 4. Security Review — Credentials & Networking

*Goal:* Audit a networking or credential-storage layer.
*Prompt Content:* `Perform a security-focused review of [file path]. This handles authentication tokens. Verify: tokens are stored in Keychain with explicit kSecAttrAccessible, SecItem* calls are not on @MainActor, URLSession.shared is not used, and HTTP status codes are validated before decoding. The project targets iOS 17.`

## 5. Navigation Refactor Review

*Goal:* Ensure NavigationStack migration is correct.
*Prompt Content:* `Review the navigation refactor in [file path]. We replaced NavigationView with NavigationStack and programmatic NavigationLink with .navigationDestination. Verify: NavigationStack uses path binding for deep linking, .navigationDestination(for:) is used instead of NavigationLink(destination:), and each tab owns its own NavigationPath.`

## 6. SwiftData Model Review

*Goal:* Review newly added SwiftData models before merge.
*Prompt Content:* `Review the SwiftData models in [file path]. Check for: explicit deleteRule on all relationships, use of #Predicate instead of NSPredicate, @Index on high-cardinality query fields, and that ModelContext is accessed via @Environment(\.modelContext) in views rather than passed through initialisers.`
