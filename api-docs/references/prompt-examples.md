# API Docs — Prompt Examples

When invoking the `api-docs` agent, include the following context for best results.

## 1. New Controller Documentation
*Goal:* Generate Postman collection for a new controller.
*Prompt Content:* `Analyze [ControllerFile] and generate a Postman Collection v2.1.0 JSON. The base URL variable is {{base_url}}, auth uses Bearer {{token}}. Group endpoints under a "[Resource Name]" folder. Include example request bodies derived from the FormRequest/Zod validation rules.`

## 2. Existing Collection Update
*Goal:* Add new endpoints to an existing Postman collection.
*Prompt Content:* `Update the Postman collection for our API. New endpoints were added in [file path]: [list of routes]. Existing collection base structure uses {{base_url}} and {{auth_token}}. Generate only the new endpoint items to merge into the existing collection.`

## 3. Full Module Documentation
*Goal:* Document all endpoints in a module.
*Prompt Content:* `Generate a complete Postman Collection v2.1.0 for the [Orders / Users / Products] module. Read all route files in [directory path]. Group by resource. Include: query parameters, path parameters, request body with field types derived from validation, and sample success/error responses.`

## 4. Auth Flow Documentation
*Goal:* Document authentication endpoints.
*Prompt Content:* `Document the authentication flow endpoints in [file path]: login, refresh token, logout, and password reset. Show: request body fields (from validation rules), success response structure (include token format), and error response format (422 validation, 401 unauthorized).`

## 5. AJAX / WordPress Endpoints
*Goal:* Document WordPress AJAX handlers.
*Prompt Content:* `Document the WordPress AJAX handlers in [file path]. For each wp_ajax_ action: document the action name (used as ?action= param), required POST parameters (from $_POST checks and sanitize calls), nonce field name, and expected JSON response format.`
