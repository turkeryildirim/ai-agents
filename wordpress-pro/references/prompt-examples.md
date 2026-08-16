# WordPress Pro — Prompt Examples

When invoking the `wordpress-pro` agent, include the following context for best results.

## 1. Custom Block
*Goal:* Build a block the modern way.
*Prompt Content:* `Build a [purpose] block for our [plugin/theme]. Use block.json registration, [static|dynamic] rendering, and InnerBlocks if [needed]. Project prefix is [prefix], text domain [domain], WP floor [version]. Include the deprecation entry if the saved markup differs from an existing version.`

## 2. Plugin Security Audit
*Goal:* Close the nonce/capability/escaping gaps.
*Prompt Content:* `Audit [plugin directory] for WordPress security. Check capability checks, nonce verification, input sanitization, output escaping by context, `$wpdb->prepare()` usage, and REST `permission_callback`s. Report each gap with file:line, the exploit path, and the fix. Cite rule ids.`

## 3. REST Endpoint
*Goal:* Register a route with a real schema.
*Prompt Content:* `Register a REST route for [purpose] in namespace [ns/v1]. Define the full args schema with sanitize and validate callbacks, a real permission_callback based on [capability], and the response shape. Handle errors with WP_Error and the right status codes.`

## 4. Query Performance
*Goal:* Cut the cost of a slow archive.
*Prompt Content:* `The [page/query] is slow — code in [file]. Find unbounded WP_Query calls, expensive meta queries, and repeated work that should be cached. Fix with bounded queries, object cache or transients with an explicit invalidation trigger, and tell me what to index if custom tables are involved.`

## 5. Block Theme Setup
*Goal:* Move theme config into theme.json.
*Prompt Content:* `Set up [theme] as a block theme. Produce theme.json with the color palette, typography scale, spacing, and layout settings from [design source], plus the required templates and template parts. Tell me which classic-theme functions become unnecessary.`
