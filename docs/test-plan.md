# Test Plan — ShopEasy Demo Store

## 1. Objective

Verify that the ShopEasy demonstration store supports reliable login, product discovery, cart management, promotional discounts, and checkout validation. Testing also aims to identify risks that could prevent a customer from completing an accurate order.

## 2. Scope

### In scope

- Valid and invalid login
- Required-field validation
- Product search and category filters
- Adding products to the cart
- Quantity boundaries from 1 through 5
- Cart subtotal calculation
- Promotional-code rules
- Checkout-field validation

### Out of scope

- Account creation and password recovery
- Payment-provider integration
- Database persistence
- Email notifications
- Performance, security penetration, and accessibility certification
- Mobile-native applications

## 3. Test basis

| ID | Requirement |
|---|---|
| REQ-01 | A registered user can log in with valid credentials. |
| REQ-02 | Invalid credentials or empty login fields must not grant access and must display an error. |
| REQ-03 | Search returns products whose names contain the entered text, ignoring case. |
| REQ-04 | Category filtering displays only products in the selected category. |
| REQ-05 | A product can be added to the cart and starts with quantity 1. |
| REQ-06 | Cart quantity accepts whole numbers from 1 to 5 only. |
| REQ-07 | The subtotal equals the sum of product price multiplied by quantity. |
| REQ-08 | SAVE10 applies a 10% discount when subtotal is at least $50; invalid or ineligible codes do not discount the order. |
| REQ-09 | Checkout requires a non-empty full name, a syntactically valid email address, and a non-empty address. |
| REQ-10 | A valid checkout displays confirmation and prevents submission when the cart is empty. |

## 4. Approach

- Use equivalence partitions for valid/invalid credentials, search data, and checkout data.
- Apply boundary value analysis to cart quantities 0, 1, 5, and 6 and the $50 promotion threshold.
- Use a decision table for valid-code/eligible-subtotal combinations.
- Perform exploratory testing around field formatting, repeated actions, and state changes.
- Prioritize checkout blockers and incorrect monetary calculations as high risk.

## 5. Environment

- Application: local `app/index.html`
- Browsers: latest available Chrome or Edge on Windows 11
- Test data: products and credentials embedded in the demo

## 6. Entry criteria

- Requirements are available and reviewed.
- The application opens without a browser error.
- Supported browser and test credentials are available.

## 7. Exit criteria

- All planned high-priority tests are executed.
- No open critical defect remains.
- High-severity defects are documented and considered in the release decision.
- A test summary report is completed.

## 8. Risks and mitigations

| Risk | Impact | Mitigation |
|---|---|---|
| Incorrect totals or discounts | Customer overcharge/undercharge | Prioritize calculation and boundary tests |
| Checkout accepts invalid data | Bad orders and contact failures | Negative and equivalence-partition tests |
| Local app differs by browser | Inconsistent behavior | Smoke-test in Chrome and Edge |
| Limited project time | Important paths untested | Execute high-risk tests first |

## 9. Deliverables

- Test cases with expected and actual results
- Defect reports
- Requirements traceability matrix
- Test summary report

