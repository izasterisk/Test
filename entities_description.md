# Entities Description

## Table 4.2 : Table Descriptions

| # | Entity | Description |
|---|--------|-------------|
| 1 | Address | Contains address information for users, farms, and orders.<br/>- Primary keys: id<br/>- Foreign keys: |
| 2 | BatchInventory | Tracks incoming inventory (stock in) - simplified version. Monitors batch and lot numbers for products.<br/>- Primary keys: id<br/>- Foreign keys: product_id, vendor_id, quality_checked_by |
| 3 | Cart | Shopping cart for customers.<br/>- Primary keys: id<br/>- Foreign keys: customer_id |
| 4 | CartItem | Individual items in a shopping cart.<br/>- Primary keys: id<br/>- Foreign keys: cart_id, product_id |
| 5 | Cashout | Cashout-specific data - approval workflow and reference tracking. Core data (amount, status, user_id, bank_account_id) resides in transactions table.<br/>- Primary keys: id<br/>- Foreign keys: transaction_id |
| 6 | ChatbotConversation | Chatbot conversation sessions.<br/>- Primary keys: id<br/>- Foreign keys: customer_id |
| 7 | ChatbotMessage | Individual chatbot messages.<br/>- Primary keys: id<br/>- Foreign keys: conversation_id |
| 8 | ContentBlock | Content block for mixed content in forum posts (embedded object, not a table).<br/>- Primary keys: N/A<br/>- Foreign keys: N/A |
| 9 | Crop | Crop information for farm profiles.<br/>- Primary keys: id<br/>- Foreign keys: farm_profile_id |
| 10 | EnergyUsage | Energy usage data linked to environmental data.<br/>- Primary keys: id<br/>- Foreign keys: environmental_data_id |
| 11 | EnvironmentalDatum | Manual environmental data input by farmers.<br/>- Primary keys: id<br/>- Foreign keys: farm_profile_id, customer_id |
| 12 | ExportInventory | Export inventory tracking (stock out) - supports both machinery (with serial) and fertilizer (with lot number).<br/>- Primary keys: id<br/>- Foreign keys: product_id, product_serial_id, order_detail_id, created_by |
| 13 | FarmProfile | Farm profile details for farmer users.<br/>- Primary keys: id<br/>- Foreign keys: user_id, address_id |
| 14 | Fertilizer | Fertilizer usage data linked to environmental data.<br/>- Primary keys: id<br/>- Foreign keys: environmental_data_id |
| 15 | ForumCategory | Forum discussion categories.<br/>- Primary keys: id<br/>- Foreign keys: |
| 16 | ForumComment | Forum post comments.<br/>- Primary keys: id<br/>- Foreign keys: forum_post_id, user_id, parent_id |
| 17 | ForumPost | Forum discussion posts.<br/>- Primary keys: id<br/>- Foreign keys: forum_category_id, user_id |
| 18 | MediaLink | Centralized media storage for multiple entity types.<br/>- Primary keys: id<br/>- Foreign keys: owner_id (polymorphic based on owner_type) |
| 19 | Notification | User notifications for system events.<br/>- Primary keys: id<br/>- Foreign keys: user_id |
| 20 | Order | Customer orders.<br/>- Primary keys: id<br/>- Foreign keys: customer_id, address_id |
| 21 | OrderDetail | Order line items.<br/>- Primary keys: id<br/>- Foreign keys: order_id, product_id |
| 22 | Payment | Payments table - stores payment gateway specific information only. Amount, status, order_id, gateway_payment_id are in transactions table.<br/>- Primary keys: id<br/>- Foreign keys: transaction_id |
| 23 | Product | Green agricultural equipment products.<br/>- Primary keys: id<br/>- Foreign keys: category_id, vendor_id, registration_id |
| 24 | ProductCategory | Hierarchical product categories.<br/>- Primary keys: id<br/>- Foreign keys: parent_id |
| 25 | ProductCertificate | Product sustainability credentials uploaded for verification.<br/>- Primary keys: id<br/>- Foreign keys: product_id, verified_by, registration_id |
| 26 | ProductRegistration | Product registration requests from vendors.<br/>- Primary keys: id<br/>- Foreign keys: vendor_id, category_id, approved_by |
| 27 | ProductReview | Product reviews and ratings.<br/>- Primary keys: id<br/>- Foreign keys: product_id, order_id, customer_id |
| 28 | ProductSerial | Manages serial numbers for individual machinery/equipment products in a batch.<br/>- Primary keys: id<br/>- Foreign keys: batch_inventory_id, product_id |
| 29 | Request | Generic requests table for various request types (refund, support).<br/>- Primary keys: id<br/>- Foreign keys: user_id, processed_by |
| 30 | RequestMessage | Request messages table for storing conversations between user and admin/staff.<br/>- Primary keys: id<br/>- Foreign keys: request_id, staff_id |
| 31 | Transaction | Central financial ledger - single source of truth for all money movements. Stores: amount, status, bank_account_id, gateway_payment_id, timestamps.<br/>- Primary keys: id<br/>- Foreign keys: user_id, order_id, bank_account_id, created_by, processed_by |
| 32 | User | Base user authentication and profile table.<br/>- Primary keys: id<br/>- Foreign keys: |
| 33 | UserAddress | Junction table linking users to their addresses.<br/>- Primary keys: id<br/>- Foreign keys: user_id, address_id |
| 34 | UserBankAccount | Bank accounts for all users (customers and vendors).<br/>- Primary keys: id<br/>- Foreign keys: user_id |
| 35 | VendorCertificate | Vendor uploaded sustainability certificates for verification.<br/>- Primary keys: id<br/>- Foreign keys: vendor_id, verified_by |
| 36 | VendorProfile | Vendor/seller profile and verification details.<br/>- Primary keys: id<br/>- Foreign keys: user_id, verified_by |
| 37 | Wallet | Vendor wallets tracking balances.<br/>- Primary keys: id<br/>- Foreign keys: vendor_id, last_updated_by |
