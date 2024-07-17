# Requirements for Products and Inventory Application
This application is comprised of an in memory SQLite database that is loaded with seed data from flat files. The database should be created on startup.
You can access the database structure using VS Code SQLite extension and pointing to the testing.db file in the ./SrDevTest/SeedData/testing.db file where you cloned this repo.
The EF Context is created and all the models necessary to query entities. One DTO is created for Product. 

Pick two issues from below, explain why you picked those two and then get started. 

Framework = .Net 8

## Issue - 1

- As an API consumer, I would like to read, write, and delete from the product selections in my product catalog. 
    - Acceptance Criteria:
        - Should be able to create, read all, read one, update, and delete a product
   - Bonus: Search by product name, id or SKU

## Issue - 2
- Technical Debt Spike
- There is not authorization on this API endpoint
    - Stand up a simple JWT workflow to authorize users to the API
-Acceptance Criteria
    -  There is a user table that stores usernames, emails and hashed and salted passwords. 
     - Created and modified dates
     - When a user authorizes via a token API endpoint they should be able to use that token to make the API call

## Issue - 3
- As an Inventory User, I would like to start a cycle count
- Acceptance Criteria
    - Should have a cycle count data and seed data to populate for testing
    - Should have an endpoint to insert a new cycle count record
    - Fields:
        - UserId
        - StartDate
        - LocationId
        - ProductId
        - RecordedCount
        - EndDate

## Issue - 4
- As an Inventory Manager, I would like a list of counts on product items that are different from the actual inventory

Report Fields:

 *  Location Code (LocationName - Shelf - Bin)
 *  Product Number
 *  Product Description
 *  Inventory Quantity
 *  Count Quantity 
 *  Variance
 *  User Who Counted

Filters:

 *  Location ID
 *  Product ID
 *  User ID


Verify:

 *  The variance for the location is correct
 *  The inventory and count quantity match for the product id
 *  The API filter work as specified
 *  Only pulls back items that had discrepancies



 ## Issue - 5
 - As an Inventory Manager, I would like to pull a stock report for a specific range.
 - Acceptance Criteria:
    - Overstock = Inventory is greater than the Product Usage for a date range
   - Understock = Inventory is less than the Product Usage for a date range

    - Filtering:

         *  Date Range
         *  Product number

    * Report needs the following fields:

        *  Product Location
        *  Product Number
        *  Quantity OnHand
        *  Consumption Quantity
        *  Percentage of Overage


Verify:

 *  That the report correctly calculates the consumption and inventory quantity.
 *  That the percentage returns correctly
 *  That the filters correctly filter the data




