# API Docs — Prompt Examples

When invoking the `api-docs` agent, include the following context for best results.

## 1. New Controller Documentation
*Goal:* Generate a Postman collection for a new controller.
*Prompt Content:* `Analyze [ControllerFile] and generate a Postman Collection v2.1.0 JSON. Base URL variable {{base_url}}, auth Bearer {{token}}. Group endpoints under a "[Resource Name]" folder. Derive request bodies from the FormRequest/Zod rules and cite the file each field came from. Include validation-error and unauthorized responses.`

## 2. Existing Collection Update
*Goal:* Add new endpoints without churning the existing file.
*Prompt Content:* `New endpoints were added in [file path]: [list]. The existing collection uses {{base_url}} and {{auth_token}}. Emit ONLY the new items in a shape I can merge — do not regenerate or reorder the whole collection.`

## 3. Full Module Documentation
*Goal:* Document every endpoint in a module.
*Prompt Content:* `Generate a complete Postman Collection v2.1.0 for the [module] module. Read all route files in [directory]. Group by resource. Include query params, path params, request bodies with types derived from validation, and sample success plus error responses. End with a coverage table and a list of anything skipped.`

## 4. Auth Flow Documentation
*Goal:* Document the authentication lifecycle.
*Prompt Content:* `Document the authentication endpoints in [file path]: login, refresh, logout, password reset. Show request body fields derived from validation rules, the success response including token format, and the error responses (422 validation, 401 unauthorized). Add a Postman test script that stores the token into {{token}}.`

## 5. WordPress AJAX / REST Endpoints
*Goal:* Document WP-specific handlers.
*Prompt Content:* `Document the WordPress handlers in [file path]. For each `wp_ajax_` action: the action name as the ?action= param, required POST parameters derived from the $_POST checks and sanitize calls, the nonce field name, and the JSON response shape. For `register_rest_route` calls, document the namespace, route, methods, args schema, and permission_callback.`
