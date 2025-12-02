# UNIT TEST FUNCTIONS LIST

## Project Information

| Item | Description |
|------|-------------|
| **Project Name** | VerdantTech Solution |
| **Document Type** | Unit Test Functions List |
| **Version** | 1.1 |
| **Created Date** | 2025-12-02 |
| **Last Updated** | 2025-12-02 |

---

## Summary Statistics

| Category | Count |
|----------|-------|
| **Total Functions** | 20 |
| **Priority** | Critical Business Logic |

---

## Core Functions List (Top 20)

| No | Function Code | Function Name | Class Name | Lines | Sheet Name |
|----|---------------|---------------|------------|-------|------------|
| 1 | AUTH-001 | LoginAsync | AuthService | ~40 | AUTH_Login |
| 2 | AUTH-002 | RegisterAsync (CreateUserAsync) | UserService | ~45 | AUTH_Register |
| 3 | AUTH-003 | ChangePassword | AuthService | ~35 | AUTH_ChangePassword |
| 4 | ORD-001 | CreateOrderAsync | OrderService | ~120 | ORD_Create |
| 5 | ORD-002 | ProcessOrderAsync | OrderService | ~60 | ORD_Process |
| 6 | CART-001 | AddToCartAsync | CartService | ~45 | CART_Add |
| 7 | CART-002 | UpdateCartItemQuantityAsync | CartService | ~50 | CART_Update |
| 8 | VP-001 | CreateAsync | VendorProfileService | ~100 | VP_Create |
| 9 | VP-002 | ApproveAsync | VendorProfileService | ~60 | VP_Approve |
| 10 | VP-003 | RejectAsync | VendorProfileService | ~50 | VP_Reject |
| 11 | PRD-001 | UpdateAsync | ProductService | ~60 | PRD_Update |
| 12 | PREG-001 | CreateAsync | ProductRegistrationService | ~120 | PREG_Create |
| 13 | PREG-002 | ChangeStatusAsync | ProductRegistrationService | ~150 | PREG_ChangeStatus |
| 14 | WAL-001 | CreateWalletCashoutRequestAsync | WalletService | ~50 | WAL_CreateCashout |
| 15 | WAL-002 | ProcessWalletCashoutRequestAsync | WalletService | ~70 | WAL_ProcessCashout |
| 16 | CASH-001 | CreateCashoutRefundAsync | CashoutService | ~100 | CASH_Refund |
| 17 | BINV-001 | CreateAsync | BatchInventoryService | ~50 | BINV_Create |
| 18 | FP-001 | CreateFarmProfileAsync | FarmProfileService | ~60 | FP_Create |
| 19 | PREV-001 | CreateProductReviewAsync | ProductReviewService | ~60 | PREV_Create |
| 20 | REQ-001 | CreateRequestAsync | RequestService | ~40 | REQ_Create |

---

## Record of Change

| Version | Date | Author | Description |
|---------|------|--------|-------------|
| 1.0 | 2025-12-02 | Team | Initial version - 70 functions |
| 1.1 | 2025-12-02 | Team | Simplified to top 25 critical functions |
| 1.2 | 2025-12-02 | Team | Reduced to top 20 critical functions |

