# VerdantTech Database Schema Documentation

## Table Descriptions

### 1. User

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table. It's a unique identifier for each specific user record. |
| 2 | email | This field stores the email address of the user. It's unique and required for user authentication and communication. |
| 3 | password_hash | This field stores the hashed password for secure authentication. The actual password is never stored in plain text. |
| 4 | role | This field specifies the user's role in the system (Customer, Staff, Vendor, or Admin). It determines their access permissions. |
| 5 | full_name | This field stores the full name of the user as displayed throughout the system. |
| 6 | phone_number | This field stores the contact phone number of the user for communication and verification purposes. |
| 7 | tax_code | This field stores the tax identification number for business users (vendors), used for tax reporting. |
| 8 | is_verified | This is a boolean flag indicating whether the user's email has been verified (true/false). |
| 9 | verification_token | This field stores a unique token sent to the user's email for account verification. |
| 10 | verification_sent_at | This is a timestamp that records the exact date and time when the verification email was sent. |
| 11 | avatar_url | This field stores the URL to the user's profile picture hosted on a cloud storage service. |
| 12 | status | This field indicates the current account status (Active, Inactive, Suspended, or Deleted). |
| 13 | last_login_at | This is a timestamp that records when the user last logged into the system. |
| 14 | refresh_token | This field stores the JWT refresh token used for maintaining user sessions without re-authentication. |
| 15 | refresh_token_expires_at | This is a timestamp indicating when the refresh token will expire and need renewal. |
| 16 | created_at | This is a timestamp that records the exact date and time when the user account was initially created. |
| 17 | updated_at | This timestamp is automatically updated every time the user record is modified. It helps track the last time a specific user was changed. |
| 18 | deleted_at | This timestamp records when the user account was soft-deleted (null if active). |

### 2. Address

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each specific address record. |
| 2 | location_address | This field stores the detailed street address or specific location information. |
| 3 | province | This field stores the province name where the address is located. |
| 4 | district | This field stores the district name within the province. |
| 5 | commune | This field stores the commune/ward name within the district. |
| 6 | province_code | This field stores the standardized code for the province for system integration. |
| 7 | district_code | This field stores the standardized code for the district for system integration. |
| 8 | commune_code | This field stores the standardized code for the commune for system integration. |
| 9 | latitude | This field stores the geographical latitude coordinate for mapping purposes (decimal precision 10,8). |
| 10 | longitude | This field stores the geographical longitude coordinate for mapping purposes (decimal precision 11,8). |
| 11 | created_at | This is a timestamp that records the exact date and time when the address record was created. |
| 12 | updated_at | This timestamp is automatically updated every time the address record is modified. |

### 3. User Address

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each user-address relationship record. |
| 2 | user_id | This is a foreign key that links to the users table. It identifies which user owns this address. |
| 3 | address_id | This is a foreign key that links to the addresses table. It connects a user to their saved address. |
| 4 | is_deleted | This is a boolean flag indicating whether this user-address link has been soft-deleted (true/false). |
| 5 | created_at | This is a timestamp that records the exact date and time when the user-address relationship was created. |
| 6 | updated_at | This timestamp is automatically updated every time the relationship record is modified. |
| 7 | deleted_at | This timestamp records when the user-address link was soft-deleted (null if active). |

### 4. Vendor Profile

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each specific vendor profile record. |
| 2 | user_id | This is a foreign key that links to the users table. It connects the vendor profile to a specific user account. |
| 3 | company_name | This field stores the registered business name of the vendor company. |
| 4 | slug | This field stores a URL-friendly version of the company name used for routing and SEO. |
| 5 | business_registration_number | This field stores the official business registration number issued by government authorities. |
| 6 | notes | This field stores additional notes or comments about the vendor for internal reference. |
| 7 | verified_at | This is a timestamp that records when the vendor profile was verified by staff/admin (null if not verified). |
| 8 | verified_by | This is a foreign key linking to the users table, indicating which staff member verified this vendor. |
| 9 | created_at | This is a timestamp that records the exact date and time when the vendor profile was created. |
| 10 | updated_at | This timestamp is automatically updated every time the vendor profile is modified. |

### 5. Farm Profile

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each specific farm profile record. |
| 2 | user_id | This is a foreign key that links to the users table. It identifies which farmer user owns this farm. |
| 3 | farm_name | This field stores the name of the farm as registered by the farmer. |
| 4 | farm_size_hectares | This field stores the total area of the farm measured in hectares. |
| 5 | address_id | This is a foreign key that links to the addresses table, indicating the physical location of the farm. |
| 6 | status | This field indicates the current operational status of the farm (Active, Maintenance, or Deleted). |
| 7 | created_at | This is a timestamp that records the exact date and time when the farm profile was created. |
| 8 | updated_at | This timestamp is automatically updated every time the farm profile is modified. |

### 6. Product Category

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each specific product category record. |
| 2 | parent_id | This is a foreign key that links to another category in this same table, enabling hierarchical category structures. |
| 3 | name | This field stores the display name of the product category. |
| 4 | slug | This field stores a URL-friendly version of the category name used for routing and SEO. |
| 5 | description | This field provides a detailed explanation of what products belong in this category. |
| 6 | is_active | This is a boolean flag indicating whether the category is currently active and visible (true/false). |
| 7 | serial_required | This is a boolean flag indicating whether products in this category require individual serial number tracking. |
| 8 | created_at | This is a timestamp that records the exact date and time when the category was created. |
| 9 | updated_at | This timestamp is automatically updated every time the category is modified. |

### 7. Product

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each specific product record. |
| 2 | category_id | This is a foreign key that links to the product_categories table. It classifies the product into a specific category. |
| 3 | vendor_id | This is a foreign key that links to the users table. It identifies which vendor is selling this product. |
| 4 | product_code | This field stores a unique code or SKU for the product used for inventory and identification. |
| 5 | product_name | This field stores the display name of the product as shown to customers. |
| 6 | slug | This field stores a URL-friendly version of the product name used for routing and SEO. |
| 7 | description | This field provides a detailed explanation of the product features, benefits, and specifications. |
| 8 | unit_price | This field stores the base selling price per unit of the product. |
| 9 | commission_rate | This field stores the percentage commission rate that the platform takes from each sale. |
| 10 | discount_percentage | This field stores the current discount percentage applied to this product (0 if no discount). |
| 11 | energy_efficiency_rating | This field stores the energy efficiency rating from 0-5, with 5 being most efficient (for applicable products). |
| 12 | specifications | This field stores technical specifications as JSON key-value pairs (e.g., {"power": "1000W", "voltage": "220V"}). |
| 13 | manual_urls | This field stores comma-separated URLs to product manuals and documentation. |
| 14 | public_url | This field stores a publicly accessible URL for the product manual document. |
| 15 | warranty_months | This field stores the warranty period in months (default is 12 months). |
| 16 | stock_quantity | This field stores the current available stock quantity for this product. |
| 17 | weight_kg | This field stores the weight of the product in kilograms, used for shipping calculations. |
| 18 | dimensions_cm | This field stores the product dimensions (length, width, height) as JSON object. |
| 19 | is_active | This is a boolean flag indicating whether the product is currently available for sale (true/false). |
| 20 | view_count | This field tracks the total number of times this product has been viewed by customers. |
| 21 | sold_count | This field tracks the total number of units of this product that have been sold. |
| 22 | rating_average | This field stores the calculated average rating from customer reviews (0.00 to 5.00). |
| 23 | registration_id | This is a foreign key linking to product_registrations table (nullable), connecting to the original registration request. |
| 24 | created_at | This is a timestamp that records the exact date and time when the product was created. |
| 25 | updated_at | This timestamp is automatically updated every time the product record is modified. |

### 8. Product Registration

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each product registration request record. |
| 2 | vendor_id | This is a foreign key that links to the users table. It identifies which vendor submitted this registration. |
| 3 | category_id | This is a foreign key that links to the product_categories table. It indicates the proposed category for the product. |
| 4 | proposed_product_code | This field stores the vendor's proposed unique product code for the new product. |
| 5 | proposed_product_name | This field stores the vendor's proposed name for the new product. |
| 6 | description | This field provides a detailed explanation of the proposed product features and benefits. |
| 7 | unit_price | This field stores the proposed selling price per unit. |
| 8 | energy_efficiency_rating | This field stores the proposed energy efficiency rating (0-5) for the product. |
| 9 | specifications | This field stores proposed technical specifications as JSON key-value pairs. |
| 10 | manual_urls | This field stores URLs to proposed product manuals and documentation. |
| 11 | public_url | This field stores a publicly accessible URL for the proposed product manual. |
| 12 | warranty_months | This field stores the proposed warranty period in months. |
| 13 | weight_kg | This field stores the proposed weight of the product in kilograms. |
| 14 | dimensions_cm | This field stores the proposed product dimensions (length, width, height) as JSON object. |
| 15 | status | This field indicates the current status of the registration request (Pending, Approved, or Rejected). |
| 16 | rejection_reason | This field stores the reason why the registration was rejected (null if approved or pending). |
| 17 | approved_by | This is a foreign key linking to users table, indicating which staff member approved this registration. |
| 18 | created_at | This is a timestamp that records when the registration request was submitted. |
| 19 | updated_at | This timestamp is automatically updated every time the registration record is modified. |
| 20 | approved_at | This is a timestamp that records when the registration was approved (null if not approved). |

### 9. Product Certificate

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each product certificate record. |
| 2 | product_id | This is a foreign key that links to the products table. It identifies which product this certificate belongs to (nullable). |
| 3 | certification_code | This field stores the unique code or identifier of the certification standard (e.g., "ISO-9001"). |
| 4 | certification_name | This field stores the full name of the certification (e.g., "ISO 9001 Quality Management"). |
| 5 | status | This field indicates the verification status of the certificate (Pending, Verified, or Rejected). |
| 6 | rejection_reason | This field stores the reason why the certificate was rejected by staff (null if verified or pending). |
| 7 | uploaded_at | This is a timestamp that records when the certificate was initially uploaded by the vendor. |
| 8 | verified_at | This is a timestamp that records when the certificate was verified by staff (null if not verified). |
| 9 | verified_by | This is a foreign key linking to users table, indicating which staff member verified this certificate. |
| 10 | created_at | This is a timestamp that records when the certificate record was created. |
| 11 | updated_at | This timestamp is automatically updated every time the certificate record is modified. |
| 12 | registration_id | This is a foreign key linking to product_registrations table (nullable), for certificates submitted during registration. |

### 10. Vendor Certificate

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each vendor certificate record. |
| 2 | vendor_id | This is a foreign key that links to the users table. It identifies which vendor this certificate belongs to. |
| 3 | certification_code | This field stores the unique code or identifier of the certification standard. |
| 4 | certification_name | This field stores the full name of the certification. |
| 5 | status | This field indicates the verification status of the certificate (Pending, Verified, or Rejected). |
| 6 | rejection_reason | This field stores the reason why the certificate was rejected by staff (null if verified or pending). |
| 7 | uploaded_at | This is a timestamp that records when the certificate was initially uploaded by the vendor. |
| 8 | verified_at | This is a timestamp that records when the certificate was verified by staff (null if not verified). |
| 9 | verified_by | This is a foreign key linking to users table, indicating which staff member verified this certificate. |
| 10 | created_at | This is a timestamp that records when the certificate record was created. |
| 11 | updated_at | This timestamp is automatically updated every time the certificate record is modified. |

### 11. Batch Inventory

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each batch inventory record. |
| 2 | product_id | This is a foreign key that links to the products table. It identifies which product this batch belongs to. |
| 3 | sku | This field stores the Stock Keeping Unit code for this specific batch. |
| 4 | vendor_id | This is a foreign key that links to the users table. It identifies which vendor supplied this batch (nullable). |
| 5 | batch_number | This field stores a unique identifier for this production/import batch. |
| 6 | lot_number | This field stores the lot number assigned by the manufacturer or supplier. |
| 7 | quantity | This field stores the total quantity of items in this batch. |
| 8 | unit_cost_price | This field stores the cost price per unit paid by the vendor to acquire this batch. |
| 9 | expiry_date | This field stores the expiration date for perishable products (null for non-perishable items). |
| 10 | manufacturing_date | This field stores the date when this batch was manufactured (nullable). |
| 11 | quality_check_status | This field indicates the quality inspection status (NotRequired, Pending, Passed, or Failed). |
| 12 | quality_checked_by | This is a foreign key linking to users table, indicating which staff member performed quality check. |
| 13 | quality_checked_at | This is a timestamp recording when the quality check was performed (null if not checked). |
| 14 | notes | This field stores additional notes or comments about this batch for reference. |
| 15 | created_at | This is a timestamp that records when the batch inventory record was created. |
| 16 | updated_at | This timestamp is automatically updated every time the batch record is modified. |

### 12. Product Serial

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each serial number record. |
| 2 | batch_inventory_id | This is a foreign key that links to the batch_inventories table. It identifies which batch this serial belongs to. |
| 3 | product_id | This is a foreign key that links to the products table. It identifies which product this serial number belongs to. |
| 4 | serial_number | This field stores the unique serial number assigned to this individual product unit. |
| 5 | status | This field indicates the current status of this serial (Stock, Sold, Refund, or Adjustment). |
| 6 | created_at | This is a timestamp that records when the serial number was registered in the system. |
| 7 | updated_at | This timestamp is automatically updated every time the serial record is modified. |

### 13. Export Inventory

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each export/stock-out record. |
| 2 | product_id | This is a foreign key that links to the products table. It identifies which product is being exported. |
| 3 | product_serial_id | This is a foreign key that links to product_serials table (nullable, for serialized products only). |
| 4 | lot_number | This field stores the lot number of the batch being exported. |
| 5 | order_detail_id | This is a foreign key that links to order_details table (nullable, for sales transactions). |
| 6 | quantity | This field stores the quantity of items being exported (default is 1 for serialized items). |
| 7 | refund_quantity | This field stores the quantity returned/refunded from this export (default is 0). |
| 8 | movement_type | This field indicates the reason for export (Sale, ReturnToVendor, Damage, Loss, or Adjustment). |
| 9 | notes | This field stores additional information about this export transaction. |
| 10 | created_by | This is a foreign key linking to users table, indicating who created this export record. |
| 11 | created_at | This is a timestamp that records when the export transaction occurred. |
| 12 | updated_at | This timestamp is automatically updated every time the export record is modified. |

### 14. Cart

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each customer's cart. |
| 2 | customer_id | This is a foreign key that links to the users table. It identifies which customer owns this cart. |
| 3 | created_at | This is a timestamp that records when the cart was created. |
| 4 | updated_at | This timestamp is automatically updated every time the cart is modified. |

### 15. Cart Item

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each item in a cart. |
| 2 | cart_id | This is a foreign key that links to the carts table. It identifies which cart this item belongs to. |
| 3 | product_id | This is a foreign key that links to the products table. It identifies which product is in the cart. |
| 4 | quantity | This field stores how many units of this product the customer wants to purchase (minimum 1). |
| 5 | created_at | This is a timestamp that records when this item was added to the cart. |
| 6 | updated_at | This timestamp is automatically updated every time the cart item is modified. |

### 16. Order

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each customer order. |
| 2 | customer_id | This is a foreign key that links to the users table. It identifies which customer placed this order. |
| 3 | status | This field indicates the current order status (Pending, Processing, Paid, Shipped, Delivered, Cancelled, or Refunded). |
| 4 | subtotal | This field stores the total price of all items before taxes, shipping, and discounts. |
| 5 | tax_amount | This field stores the calculated tax amount for this order (default is 0.00). |
| 6 | shipping_fee | This field stores the delivery cost for this order (default is 0.00). |
| 7 | discount_amount | This field stores the total discount applied to this order (default is 0.00). |
| 8 | total_amount | This field stores the final amount the customer needs to pay after all calculations. |
| 9 | address_id | This is a foreign key that links to the addresses table. It specifies the delivery destination. |
| 10 | order_payment_method | This field indicates the payment method chosen (Banking or COD - Cash On Delivery). |
| 11 | shipping_method | This field stores the name of the shipping/courier service being used. |
| 12 | tracking_number | This field stores the package tracking number provided by the courier service. |
| 13 | notes | This field stores any special instructions or comments from the customer about the order. |
| 14 | courier_id | This field stores the ID of the courier service selected for delivery. |
| 15 | width | This field stores the package width in centimeters for shipping calculation. |
| 16 | height | This field stores the package height in centimeters for shipping calculation. |
| 17 | length | This field stores the package length in centimeters for shipping calculation. |
| 18 | weight | This field stores the package weight in grams for shipping calculation. |
| 19 | cancelled_reason | This field stores the explanation for why the order was cancelled (null if not cancelled). |
| 20 | cancelled_at | This is a timestamp recording when the order was cancelled (null if not cancelled). |
| 21 | confirmed_at | This is a timestamp recording when the order was confirmed by the vendor (null if not confirmed). |
| 22 | shipped_at | This is a timestamp recording when the order was shipped (null if not shipped). |
| 23 | delivered_at | This is a timestamp recording when the order was delivered to customer (null if not delivered). |
| 24 | created_at | This is a timestamp that records when the order was placed. |
| 25 | updated_at | This timestamp is automatically updated every time the order record is modified. |

### 17. Order Detail

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each line item in an order. |
| 2 | order_id | This is a foreign key that links to the orders table. It identifies which order this line item belongs to. |
| 3 | product_id | This is a foreign key that links to the products table. It identifies which product was ordered. |
| 4 | quantity | This field stores how many units of this product were ordered. |
| 5 | unit_price | This field stores the price per unit at the time of order (may differ from current price). |
| 6 | discount_amount | This field stores the discount applied to this specific line item (default is 0.00). |
| 7 | subtotal | This field stores the calculated total for this line item (quantity × unit_price - discount). |
| 8 | is_wallet_credited | This is a boolean flag indicating whether the vendor's wallet has been credited for this item (true/false). |
| 9 | updated_at | This timestamp is automatically updated every time the order detail is modified. |

### 18. Payment

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each payment record. |
| 2 | transaction_id | This is a foreign key that links to the transactions table. It connects payment details to the financial ledger. |
| 3 | payment_method | This field indicates the payment method used (CreditCard, DebitCard, Stripe, COD, or Payos). |
| 4 | payment_gateway | This field indicates which payment gateway processed this payment (Stripe, Manual, or Payos). |
| 5 | gateway_response | This field stores the raw JSON response received from the payment gateway for reference and debugging. |
| 6 | created_at | This is a timestamp that records when the payment record was created. |
| 7 | updated_at | This timestamp is automatically updated every time the payment record is modified. |

### 19. Transaction

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, serving as the unique identifier for each financial transaction. |
| 2 | transaction_type | This field indicates the type of money movement (PaymentIn, WalletCashout, Refund, or Adjustment). |
| 3 | amount | This field stores the monetary value of the transaction. |
| 4 | currency | This field stores the currency code (default is "VND" for Vietnamese Dong). |
| 5 | user_id | This is a foreign key that links to the users table. It identifies the user associated with this transaction. |
| 6 | order_id | This is a foreign key that links to the orders table (nullable, for payment-related transactions). |
| 7 | bank_account_id | This is a foreign key that links to user_bank_accounts table (nullable, for cashout transactions). |
| 8 | status | This field indicates the current transaction status (Pending, Completed, Failed, or Cancelled). |
| 9 | note | This field stores a description or note about this transaction for reference. |
| 10 | gateway_payment_id | This field stores the payment ID from the external payment gateway for tracking. |
| 11 | created_by | This is a foreign key linking to users table, indicating who initiated this transaction. |
| 12 | processed_by | This is a foreign key linking to users table, indicating which staff member processed this transaction. |
| 13 | created_at | This is a timestamp that records when the transaction was created. |
| 14 | processed_at | This is a timestamp that records when the transaction was processed (null if not processed). |
| 15 | updated_at | This timestamp is automatically updated every time the transaction record is modified. |

### 20. Cashout

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each cashout request. |
| 2 | transaction_id | This is a foreign key that links to the transactions table. It connects the cashout to the financial ledger. |
| 3 | reference_type | This field indicates the reason for cashout (VendorWithdrawal, Refund, or AdminAdjustment). |
| 4 | reference_id | This field stores an ID linking to the related entity (e.g., order_id for refunds) - nullable. |
| 5 | notes | This field stores additional information or comments about this cashout request. |
| 6 | created_at | This is a timestamp that records when the cashout request was created. |
| 7 | updated_at | This timestamp is automatically updated every time the cashout record is modified. |

### 21. Wallet

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each vendor wallet. |
| 2 | vendor_id | This is a foreign key that links to the users table. It identifies which vendor owns this wallet. |
| 3 | balance | This field stores the current available balance in the vendor's wallet (default is 0.00). |
| 4 | last_updated_by | This is a foreign key linking to users table, indicating who last modified the wallet balance. |
| 5 | created_at | This is a timestamp that records when the wallet was created. |
| 6 | updated_at | This timestamp is automatically updated every time the wallet balance is modified. |

### 22. User Bank Account

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each bank account record. |
| 2 | user_id | This is a foreign key that links to the users table. It identifies which user owns this bank account. |
| 3 | bank_code | This field stores the standardized bank code (e.g., "VCB" for Vietcombank). |
| 4 | account_number | This field stores the bank account number for receiving payments. |
| 5 | owner_name | This field stores the name of the account holder as registered with the bank. |
| 6 | is_active | This is a boolean flag indicating whether this bank account is currently active and can be used. |
| 7 | created_at | This is a timestamp that records when the bank account was added to the system. |
| 8 | updated_at | This timestamp is automatically updated every time the bank account record is modified. |

### 23. Product Review

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each product review. |
| 2 | product_id | This is a foreign key that links to the products table. It identifies which product is being reviewed. |
| 3 | order_id | This is a foreign key that links to the orders table. It ensures the reviewer actually purchased the product. |
| 4 | customer_id | This is a foreign key that links to the users table. It identifies which customer wrote this review. |
| 5 | rating | This field stores the customer's rating score from 1 to 5 stars. |
| 6 | comment | This field stores the customer's written review comments about their experience with the product. |
| 7 | created_at | This is a timestamp that records when the review was submitted. |
| 8 | updated_at | This timestamp is automatically updated every time the review is modified. |

### 24. Forum Category

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each forum category. |
| 2 | name | This field stores the display name of the forum category. |
| 3 | description | This field provides a detailed explanation of what topics belong in this category. |
| 4 | is_active | This is a boolean flag indicating whether this category is currently active and visible (true/false). |
| 5 | created_at | This is a timestamp that records when the category was created. |
| 6 | updated_at | This timestamp is automatically updated every time the category is modified. |

### 25. Forum Post

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each forum post. |
| 2 | forum_category_id | This is a foreign key that links to the forum_categories table. It classifies the post into a specific category. |
| 3 | user_id | This is a foreign key that links to the users table. It identifies who created this post. |
| 4 | title | This field stores the title/headline of the forum post. |
| 5 | slug | This field stores a URL-friendly version of the post title used for routing and SEO. |
| 6 | content | This field stores the post content as an array of content blocks (text, images, etc.) in JSON format. |
| 7 | tags | This field stores comma-separated tags/keywords for easier searching and categorization. |
| 8 | view_count | This field tracks how many times this post has been viewed by users. |
| 9 | like_count | This field tracks the total number of likes this post has received. |
| 10 | dislike_count | This field tracks the total number of dislikes this post has received. |
| 11 | is_pinned | This is a boolean flag indicating whether this post is pinned to the top of the category (true/false). |
| 12 | status | This field indicates the visibility status of the post (Visible or Hidden). |
| 13 | created_at | This is a timestamp that records when the post was created. |
| 14 | updated_at | This timestamp is automatically updated every time the post is modified. |

### 26. Forum Comment

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each forum comment. |
| 2 | forum_post_id | This is a foreign key that links to the forum_posts table. It identifies which post this comment belongs to. |
| 3 | user_id | This is a foreign key that links to the users table. It identifies who wrote this comment. |
| 4 | parent_id | This is a foreign key linking to another comment in this table (nullable), enabling nested replies. |
| 5 | content | This field stores the text content of the comment. |
| 6 | like_count | This field tracks the total number of likes this comment has received. |
| 7 | dislike_count | This field tracks the total number of dislikes this comment has received. |
| 8 | status | This field indicates the moderation status (Visible, Moderated, or Deleted). |
| 9 | created_at | This is a timestamp that records when the comment was posted. |
| 10 | updated_at | This timestamp is automatically updated every time the comment is modified. |

### 27. Chatbot Conversation

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each chatbot conversation session. |
| 2 | customer_id | This is a foreign key that links to the users table. It identifies which customer is having this conversation. |
| 3 | session_id | This field stores a unique session identifier for tracking the conversation. |
| 4 | title | This field stores a descriptive title or summary of the conversation topic. |
| 5 | context | This field stores conversation context and metadata (up to 5000 characters) for AI continuity. |
| 6 | is_active | This is a boolean flag indicating whether this conversation session is still active (true/false). |
| 7 | started_at | This is a timestamp that records when the conversation session began. |

### 28. Chatbot Message

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each individual message. |
| 2 | conversation_id | This is a foreign key that links to chatbot_conversations table. It identifies which conversation this message belongs to. |
| 3 | message_type | This field indicates who sent the message (User, Bot, or System). |
| 4 | message_text | This field stores the actual text content of the message. |
| 5 | created_at | This is a timestamp that records when the message was sent. |

### 29. Request

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each support/refund request. |
| 2 | user_id | This is a foreign key that links to the users table. It identifies who submitted this request. |
| 3 | request_type | This field indicates the type of request (RefundRequest or SupportRequest). |
| 4 | title | This field stores a brief title or summary of the request. |
| 5 | status | This field indicates the current request status (Pending, InReview, Approved, Rejected, Completed, or Cancelled). |
| 6 | processed_by | This is a foreign key linking to users table, indicating which staff member is handling this request. |
| 7 | processed_at | This is a timestamp that records when the request was processed (null if still pending). |
| 8 | created_at | This is a timestamp that records when the request was submitted. |
| 9 | updated_at | This timestamp is automatically updated every time the request is modified. |

### 30. Request Message

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each message in the request conversation. |
| 2 | request_id | This is a foreign key that links to the requests table. It identifies which request this message belongs to. |
| 3 | staff_id | This is a foreign key linking to users table (nullable), indicating which staff member replied (null if from user). |
| 4 | description | This field stores the message content from either the user or staff member. |
| 5 | reply_notes | This field stores additional internal notes about the reply (optional). |
| 6 | created_at | This is a timestamp that records when the message was sent. |
| 7 | updated_at | This timestamp is automatically updated every time the message is modified. |

### 31. Notification

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each notification. |
| 2 | user_id | This is a foreign key that links to the users table. It identifies which user should receive this notification. |
| 3 | title | This field stores the notification headline or subject. |
| 4 | message | This field stores the detailed notification message content. |
| 5 | reference_type | This field indicates what type of entity triggered this notification (Order, Payment, Request, etc.) - nullable. |
| 6 | reference_id | This field stores the ID of the entity that triggered this notification - nullable. |
| 7 | is_read | This is a boolean flag indicating whether the user has read this notification (true/false). |
| 8 | created_at | This is a timestamp that records when the notification was created. |
| 9 | updated_at | This timestamp is automatically updated every time the notification is modified. |

### 32. Crop

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each crop record. |
| 2 | farm_profile_id | This is a foreign key that links to the farm_profiles table. It identifies which farm is growing this crop. |
| 3 | crop_name | This field stores the name of the crop being cultivated. |
| 4 | planting_date | This field stores the date when the crop was planted. |
| 5 | planting_method | This field indicates the cultivation method used (direct seeding, tray nursery, transplanting, etc.). |
| 6 | crop_type | This field classifies the crop type (leafy green, fruiting, root vegetable, or herb). |
| 7 | farming_type | This field indicates the farming approach (intensive, crop rotation, intercropping, greenhouse, or hydroponics). |
| 8 | status | This field indicates the current crop status (Growing, Harvested, Failed, or Deleted). |
| 9 | created_at | This is a timestamp that records when the crop record was created. |
| 10 | updated_at | This timestamp is automatically updated every time the crop record is modified. |

### 33. Environmental Datum

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each environmental data record. |
| 2 | farm_profile_id | This is a foreign key that links to the farm_profiles table. It identifies which farm this data belongs to. |
| 3 | customer_id | This is a foreign key that links to the users table. It identifies which farmer submitted this data. |
| 4 | measurement_start_date | This field stores the date when the measurement period began. |
| 5 | measurement_end_date | This field stores the date when the measurement period ended. |
| 6 | sand_pct | This field stores the percentage of sand in the soil (0-30 cm depth) - nullable. |
| 7 | silt_pct | This field stores the percentage of silt in the soil (0-30 cm depth) - nullable. |
| 8 | clay_pct | This field stores the percentage of clay in the soil (0-30 cm depth) - nullable. |
| 9 | phh2o | This field stores the soil pH level measured in water (0-30 cm depth) - nullable. |
| 10 | precipitation_sum | This field stores the total rainfall amount in millimeters during the measurement period - nullable. |
| 11 | et0_fao_evapotranspiration | This field stores the reference evapotranspiration calculated using FAO method in millimeters - nullable. |
| 12 | co2_footprint | This field stores the estimated CO2 emissions in kilograms for this period - nullable. |
| 13 | notes | This field stores additional observations or comments about the environmental conditions. |
| 14 | created_at | This is a timestamp that records when the environmental data record was created. |
| 15 | updated_at | This timestamp is automatically updated every time the environmental data is modified. |

### 34. Fertilizer

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each fertilizer usage record. |
| 2 | environmental_data_id | This is a foreign key that links to the environmental_data table (unique one-to-one relationship). |
| 3 | organic_fertilizer | This field stores the amount of organic fertilizer used (decimal 10,2 precision). |
| 4 | npk_fertilizer | This field stores the amount of NPK (Nitrogen-Phosphorus-Potassium) fertilizer used. |
| 5 | urea_fertilizer | This field stores the amount of urea fertilizer used. |
| 6 | phosphate_fertilizer | This field stores the amount of phosphate fertilizer used. |
| 7 | created_at | This is a timestamp that records when the fertilizer usage record was created. |
| 8 | updated_at | This timestamp is automatically updated every time the fertilizer record is modified. |

### 35. Energy Usage

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each energy usage record. |
| 2 | environmental_data_id | This is a foreign key that links to the environmental_data table (unique one-to-one relationship). |
| 3 | electricity_kwh | This field stores the electricity consumption in kilowatt-hours (decimal 10,2 precision). |
| 4 | gasoline_liters | This field stores the gasoline consumption in liters. |
| 5 | diesel_liters | This field stores the diesel fuel consumption in liters. |
| 6 | created_at | This is a timestamp that records when the energy usage record was created. |
| 7 | updated_at | This timestamp is automatically updated every time the energy usage record is modified. |

### 36. Media Link

| No | Entity | Description |
|----|--------|-------------|
| 1 | id | This is the primary key for the table, a unique identifier for each media file record. |
| 2 | owner_type | This field indicates what type of entity owns this media (VendorCertificates, Products, ProductReviews, ForumPosts, etc.). |
| 3 | owner_id | This field stores the ID of the entity that owns this media file. |
| 4 | image_url | This field stores the full URL to the uploaded image or file (up to 1024 characters). |
| 5 | image_public_id | This field stores the public ID from the cloud storage service (e.g., Cloudinary) for management. |
| 6 | purpose | This field indicates the purpose of the media (None, Front, Back, ProductCertificatePdf, VendorCertificatesPdf, ProductImage). |
| 7 | sort_order | This field stores the display order when multiple media files are associated with one entity. |
| 8 | created_at | This is a timestamp that records when the media file was uploaded. |
| 9 | updated_at | This timestamp is automatically updated every time the media record is modified. |
