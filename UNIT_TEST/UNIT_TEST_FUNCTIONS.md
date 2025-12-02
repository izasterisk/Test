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
| **Total Functions** | 25 |
| **Priority** | Critical Business Logic |

---

## Core Functions List (Top 25)

| No | Function Code | Function Name | Class Name | Lines | Sheet Name |
|----|---------------|---------------|------------|-------|------------|
| 1 | AUTH-001 | LoginAsync | AuthService | ~40 | AUTH_Login |
| 2 | AUTH-002 | RegisterAsync (CreateUserAsync) | UserService | ~45 | AUTH_Register |
| 3 | AUTH-003 | ChangePassword | AuthService | ~35 | AUTH_ChangePassword |
| 4 | AUTH-004 | RefreshTokenAsync | AuthService | ~30 | AUTH_RefreshToken |
| 5 | ORD-001 | CreateOrderAsync | OrderService | ~120 | ORD_Create |
| 6 | ORD-002 | ProcessOrderAsync | OrderService | ~60 | ORD_Process |
| 7 | ORD-003 | ShipOrderAsync | OrderService | ~50 | ORD_Ship |
| 8 | CART-001 | AddToCartAsync | CartService | ~45 | CART_Add |
| 9 | CART-002 | UpdateCartItemQuantityAsync | CartService | ~50 | CART_Update |
| 10 | VP-001 | CreateAsync | VendorProfileService | ~100 | VP_Create |
| 11 | VP-002 | ApproveAsync | VendorProfileService | ~60 | VP_Approve |
| 12 | VP-003 | RejectAsync | VendorProfileService | ~50 | VP_Reject |
| 13 | PRD-001 | UpdateAsync | ProductService | ~60 | PRD_Update |
| 14 | PREG-001 | CreateAsync | ProductRegistrationService | ~120 | PREG_Create |
| 15 | PREG-002 | ChangeStatusAsync | ProductRegistrationService | ~150 | PREG_ChangeStatus |
| 16 | WAL-001 | CreateWalletCashoutRequestAsync | WalletService | ~50 | WAL_CreateCashout |
| 17 | WAL-002 | ProcessWalletCashoutRequestAsync | WalletService | ~70 | WAL_ProcessCashout |
| 18 | CASH-001 | CreateCashoutRefundAsync | CashoutService | ~100 | CASH_Refund |
| 19 | BINV-001 | CreateAsync | BatchInventoryService | ~50 | BINV_Create |
| 20 | BINV-002 | UpdateAsync | BatchInventoryService | ~50 | BINV_Update |
| 21 | FP-001 | CreateFarmProfileAsync | FarmProfileService | ~60 | FP_Create |
| 22 | CROP-001 | AddCropsToFarmAsync | CropService | ~50 | CROP_Add |
| 23 | PREV-001 | CreateProductReviewAsync | ProductReviewService | ~60 | PREV_Create |
| 24 | REQ-001 | CreateRequestAsync | RequestService | ~40 | REQ_Create |
| 25 | REQ-002 | ProcessRequestAsync | RequestService | ~60 | REQ_Process |

---

## Record of Change

| Version | Date | Author | Description |
|---------|------|--------|-------------|
| 1.0 | 2025-12-02 | Team | Initial version - 70 functions |
| 1.1 | 2025-12-02 | Team | Simplified to top 25 critical functions |

