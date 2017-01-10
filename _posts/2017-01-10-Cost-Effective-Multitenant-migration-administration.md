
You have developed a technology product for a certain usecase and want to reach B2B segment. It is always laborious work to address the multiple business's at a time & focus will be shifted to tedious work rather than reaching the technology product to the market. At the same time, you are worried about the cost structure for managing multiple businesses . 
Simplifying and enabling  the multi tenant usecase's for your application/product and without increasing the cost of the infrastructure and complexity is done through simple steps.

There are several options to simplify this usecase. 
On a quick view, let's go through in short descriptions

**Option 1:** Complete Separation of Databases: Have Master DB for knowing the companies/organizations ,owner. All the users & app data will be in each db (organization). same tables for all the organizations. On every request ,we need organizationId, userID.
Data separation using db ,easy to track the issues, audit, good for enabling pilot features for few organizations. High Costs for the end customers especially Small & medium businesses .High Operational costs.

**Option2**: Lean Approach using additional columns: Have Organization table with Org Info and owner. User table will have a composite key of organization users & organization id. This is to make sure, any user can be part of multiple organization. All the users & app data will have composite key of userId,orgId. On Every request , we need organizationId, userId. Data separation is done through rows in a table , tracking of issues needs simple UI tool to make sure info is fetched for particular org. Low Operations costs. Ability to play the price in the market. Easy to launch for small & medium businesses.  Quality Engineering time will be increased due to multiple organizations impact.

----------

DB Structure for Option2 : 
>User Table:

 - userId (alphanumerics)
 - emailId (compositeKey) (alphanumerics)
 - companyId (compositeKey)(alphanumerics) (foreignKey)
 - mobileNbr (compositeKey)(alphanumerics)
 - password (sha1)(alphanumerics)
 - confirmed (char)
 - createdDate
 - modifiedDate
 - createdBy
 - address1
 - address2
 - city
 - state
 - pin
 - isActive
 - statusDescription
 - messageId (Message to be displayed) (foreign Key)
 - roleId (foreignKey) 
 
> Company or Organization
 
 - companyId
 - CompanyName
 - createdBy
 - isPaid (Char) Y/N
 - planId (foreign Key)
 - planExpiry
 - messageId(Message to be displayed) (foreign Key)
 

>Plan or Subscription

 - planId (primary key)
 - planName
 - planCost (int)
 - planCurrency
 - planDescription
 - planUserLimits (int)
 

> Message

 - messageId(primary key)
 - messageShort Description (300 chars)
 - message Description(5000 chars)
 - createdBy
 - expiredAt
 - messageType (Security, Priority, Wishes, Reminders,TODO)

> Role Type

- roleId(Primary)
- roleName (SuperAdmin, Admin, User, visitor)
- roleDescription
- accessCode (5,10,20,25)

>Access Type ( Many to Many)

-  roleId (Composite key)
-  companyId(Composite key)
-  userId(Composite key)
-  createdAt
-  modifiedAt
