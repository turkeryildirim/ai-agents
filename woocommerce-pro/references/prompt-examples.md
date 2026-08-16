# WooCommerce Pro — Prompt Examples

When invoking the `woocommerce-pro` agent, include the following context for best results.

## 1. Custom Checkout Field
*Goal:* Add a field that survives the whole order lifecycle.
*Prompt Content:* `Add a [field] to checkout. Render it at [hook], validate it server-side, save it to order meta, display it in admin order detail and in the customer email. HPOS is [enabled/disabled]. Use CRUD objects only and cite the hooks you chose with their priority.`

## 2. Payment Gateway
*Goal:* Implement a gateway safely.
*Prompt Content:* `Build a WooCommerce payment gateway for [provider]. Implement the gateway class, settings fields, process_payment with the correct return contract, the webhook handler with signature verification and idempotency, refund support, and test mode. Explain the money and rounding handling explicitly.`

## 3. Bulk Operation Performance
*Goal:* Make a bulk job survive a large catalog.
*Prompt Content:* `This bulk operation times out with [n] products/orders: [code]. Add cache priming, eliminate per-row wc_get_product()/wc_get_order() calls, and batch the work. Show the before/after query count and tell me the safe batch size.`

## 4. Order Status Workflow
*Goal:* Add a custom status without breaking reporting.
*Prompt Content:* `Add a custom order status [name] between [status A] and [status B]. Register it, hook the transitions, make it appear in admin filters and reports, and handle the email triggering. Tell me what breaks in existing reporting and how to avoid it.`

## 5. WooCommerce Security & Integrity Review
*Goal:* Audit a commerce extension.
*Prompt Content:* `Review [extension directory]. Check for direct $wpdb access to orders/products, missing entity/ownership/status verification, unprotected stock decrements, webhook replay vulnerability, missing capability and nonce checks, and per-row getters in bulk loops. Report by severity with rule ids and fixes.`
