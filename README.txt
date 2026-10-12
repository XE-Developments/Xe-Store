XE STORE — PROFESSIONAL FRONTEND

Files: index.html, styles.css, app.js.

Deploy:
1. Back up your current GitHub repository files.
2. Replace index.html, styles.css, and app.js with these files.
3. Commit changes and wait for GitHub Pages to publish.
4. Open your Pages URL and test product loading, cart, delivery form, and Razorpay Test Mode.

Backend compatibility expected:
GET https://xe-payments.onrender.com/api/products
POST /api/orders with { customer, items: [{ productId, quantity }] }
POST /api/payments/verify with orderId, razorpay_order_id, razorpay_payment_id, razorpay_signature.
The order response should include keyId, razorpayOrderId, amount, and orderId. Verification should return verified:true or success:true only after server-side verification.

Products should include id, name, description, price_paise (paise), image_url, and optionally category and badge.

Important:
- This is a frontend replacement, not a completed production store by itself.
- Use Razorpay Test keys until end-to-end tests pass. Live payments require Razorpay account activation and Live keys stored only in Render environment variables.
- Never put Razorpay secret keys in app.js.
- Replace placeholder support email and starter policy text before launch.
- Newsletter currently displays a notice; connect it to an email service to collect subscribers.
- Admin product/order management is not included; it requires secure admin backend endpoints and an admin interface.
- Confirm server-side payment verification, webhook signature validation, duplicate-event handling and database updates before real launch.
