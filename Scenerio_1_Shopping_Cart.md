Design a program for an online store’s shopping cart system with the following requirements:

A **Cart** contains a collection (ArrayList) of **CartLine** objects. Each CartLine represents one product entry in the cart and consists of:

* A reference to a **Product**
* A quantity of that product

This means the main collection exists inside the Cart, not at a higher manager level.

A **Product** has:

* A unique SKU
* A base price
* A category, which can be **Electronics**, **Grocery**, or **Clothing**

Discounts are not stored as fixed values. Instead, they are determined dynamically based on category and quantity rules:

* **Electronics**: 10% discount on the line only if the quantity is 3 or more
* **Grocery**: Flat discount of 5 currency units per line if the quantity is 6 or more
* **Clothing**: 20% discount on the line only if the Cart contains at least 4 different lines (not total items). This means the discount depends on the overall state of the cart, not just the individual line

Each **CartLine** must be able to calculate its own subtotal after applying the appropriate discount.

The **Cart** must support the following operations:

* Add a product with a given quantity:

  * If a product with the same SKU already exists in the cart, update its quantity instead of creating a new line
* Remove a product line using its SKU
* Compute the grand total:

  * First apply all discounts
  * Then apply shipping:

    * Free shipping if the total exceeds 50 currency units
    * Otherwise, add a flat shipping fee of 5 currency units
* Display a detailed receipt showing:

  * Product information
  * Original line price
  * Discount applied
  * Final subtotal per line

A **StoreManager** class must:

* Store multiple Cart objects (one per customer) in an ArrayList
* Ensure no two carts exist for the same customer name
* Provide a method to identify which customer’s cart has the highest grand total

The program must demonstrate:

* At least two customer carts
* Each cart must contain at least three product lines from different categories
* At least one scenario where adding a fourth line enables the Clothing discount (i.e., the discount becomes applicable only after the cart reaches four lines)
* Both cases of the shipping rule:

  * One cart qualifying for free shipping
  * One cart incurring the shipping fee

The design should be flexible so that new product categories with their own discount rules can be added later with minimal changes to existing classes.


Rubrics:

| Criteria | Marks |
| --- | --- |
| 1. Use of All Principles of OOP | 3 |
| 2. Implementation of All Required Classes | 4 |
| 3. Logical Correctness / Functionality | 3 |
