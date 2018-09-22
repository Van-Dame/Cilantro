# SPEC

We want to create a restaurant management platform. The system should allow:

- **Customers**:
  - To Browse for restaurants based on proximity to their location
  - To Browse menu items of a restaurant
  - To Add menu items from a single restaurant to their cart
  - To Place order for items in their cart
  - To Make Payment for the cart items
  - To Track Delivery
  - To View Orders History
- **Restaurant Owners**:
  - To Manage their restaurant's online presence
  - To Manage the menu items available in their restaurant
  - To Manage Orders
  - To Update Delivery Status
  - To View Orders History
- **Super Administrators**:
  - To Add/Remove Restaurant
  - To Manage Restaurant Owners
  - To Bill Restaurant for using the platform

## Initial Design (Based on Spec)

The system will be built using .NET Core (v.Latest), C#, and DDD/TDD practices. It will consist of several layers including:

- #### Persistence Layer
  The persistence (database) layer will use Entity Framework Core ORM and save the data to an SQL Server database.
- #### Business Layer
  The business logic layer will consist of standard C# code encapsulating our business logic. It will return DTOs (Data Transfer Objects) rather than database model objects.
- #### API Layer
  The API Layer will be implemented using ASP&period;NET Core Web API and will communicate with business layer only. It will take DTOs returned from business layer, convert them to JSON and return to API callers.
- #### User Interface
  The User Interface will consist of following parts:
  - ##### Super Admin (React SPA)
    Management area for Super Administrators
  - ##### Restaurant (React SPA)
    Management area for Restaurant Owners. To be combined with Super Admin area with functionalities dictated by logged in user type.
  - ##### Customer (React SPA)
    Customer facing site. To be developed separately from Admin area.
