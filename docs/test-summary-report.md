# Test Summary Report — ShopEasy Demo Store

## Summary

Manual functional testing was completed against the defined login, catalog, cart, promotion, and checkout requirements. All 22 planned test cases were executed.

## Execution results

| Metric | Result |
|---|---:|
| Planned | 22 |
| Executed | 22 |
| Passed | 18 |
| Failed | 4 |
| Blocked | 0 |
| Pass rate | 81.8% |
| Requirements covered | 10 of 10 |

## Defect summary

| Severity | Open defects |
|---|---:|
| Critical | 0 |
| High | 3 |
| Medium | 1 |
| Low | 0 |

The open high-severity defects affect quantity limits, promotional pricing at a boundary, and checkout email validation. These issues could create inaccurate orders or unusable customer contact information.

## Residual risks

- Browser compatibility received only basic coverage.
- Payment processing and backend persistence are outside scope.
- Performance, security, and full accessibility testing were not performed.
- Fix confirmation and regression testing remain outstanding.

## Release recommendation

**Not recommended for release in its current state.** Resolve DEF-002, DEF-003, and DEF-004, then perform confirmation and focused regression testing. DEF-001 may be scheduled according to product priority but should remain visible as a usability risk.

