# Open/Closed Principle (OCP)
## Scenario
Now, the OrderProcessor (in your refactored design from Task 1) needs to offer new promotional discounts (e.g., buy-one-get-one-free, holiday discounts, coupon codes, etc.) without altering the existing pricing logic.

## Identify the Existing Problem
If the discount calculations are directly embedded within the existing pricing logic, any new discount type would require modifying the existing code. This violates the Open/Closed Principle, which states that software entities should be open for extension but closed for modification. Modifying existing code can introduce bugs and increase the risk of regression.

## Design an Extensible Solution
![OCP UML Diagram](link_to_ocp_uml_diagram)

## Explanation
The new design introduces an `IDiscountStrategy` interface that defines a method for applying discounts. Each specific discount type (e.g., `PercentageDiscount`, `BOGODiscount`, `CouponDiscount`) implements this interface. This allows new discount types to be added without modifying the existing pricing logic, adhering to the Open/Closed Principle. The core pricing logic can simply call the `applyDiscount()` method on the appropriate strategy, making the system more flexible and easier to extend.
