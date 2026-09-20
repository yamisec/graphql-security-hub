# GraphQL Argument Dictionary

A collection of common GraphQL argument names that may appear in real-world applications.

> Argument names are application-specific. These are common naming patterns that can help during GraphQL schema reconnaissance and security testing.

---

# 1. Object Identifiers

These arguments commonly identify the object that a query or mutation operates on.

```text
id
userId
accountId
profileId
customerId
memberId
adminId
productId
productVariantId
categoryId
orderId
orderItemId
cartId
cartItemId
paymentId
paymentMethodId
transactionId
invoiceId
subscriptionId
planId
shipmentId
deliveryId
addressId
organizationId
companyId
workspaceId
tenantId
teamId
teamMemberId
projectId
fileId
folderId
documentId
postId
articleId
commentId
messageId
conversationId
notificationId
reportId
```

---

# 2. User & Account Arguments

```text
userId
accountId
username
email
phone
profileId
memberId
customerId
accountType
status
state
```

---

# 3. Authentication Arguments

```text
username
email
password
currentPassword
newPassword
confirmPassword
code
verificationCode
otp
token
accessToken
refreshToken
sessionId
rememberMe
```

---

# 4. Authorization & Role Arguments

```text
role
roleId
roleName
permission
permissionId
permissionName
permissions
privilege
privilegeId
accessLevel
scope
scopes
organizationRole
teamRole
```

Security-interesting examples:

```text
role
roleId
permissions
permissionId
accessLevel
scope
```

These can be relevant when testing whether a user can modify their own or another user's privileges.

---

# 5. Product Arguments

```text
productId
productIds
productName
name
description
price
currency
categoryId
categoryIds
brandId
variantId
sku
quantity
status
visibility
published
```

---

# 6. Inventory Arguments

```text
inventoryId
inventoryItemId
warehouseId
productId
stock
quantity
amount
adjustment
reason
locationId
```

---

# 7. Order Arguments

```text
orderId
orderIds
orderItemId
userId
customerId
productId
quantity
status
orderStatus
paymentStatus
shippingStatus
```

---

# 8. Payment Arguments

```text
paymentId
paymentMethodId
transactionId
amount
currency
paymentStatus
paymentMethod
billingAddress
cardToken
paymentToken
invoiceId
customerId
```

---

# 9. Subscription & Billing Arguments

```text
subscriptionId
planId
plan
billingCycle
billingPeriod
startDate
endDate
trialDays
price
currency
couponCode
discountId
invoiceId
```

---

# 10. Shipping & Delivery Arguments

```text
shipmentId
deliveryId
addressId
shippingAddressId
carrierId
trackingId
trackingNumber
shippingMethod
deliveryMethod
shippingStatus
```

---

# 11. Content Arguments

```text
postId
articleId
contentId
pageId
title
body
content
description
authorId
categoryId
tagId
status
visibility
published
publishedAt
```

---

# 12. Comment Arguments

```text
commentId
postId
articleId
parentCommentId
authorId
content
body
status
```

---

# 13. Media & File Arguments

```text
fileId
fileIds
folderId
fileName
filename
path
filePath
url
mimeType
contentType
size
mediaId
documentId
attachmentId
```

---

# 14. Organization Arguments

```text
organizationId
companyId
workspaceId
tenantId
organizationName
companyName
memberId
memberIds
ownerId
role
roleId
```

---

# 15. Team Arguments

```text
teamId
teamMemberId
memberId
userId
role
roleId
permission
permissionId
invitationId
```

---

# 16. API & Developer Arguments

```text
apiKeyId
apiKey
token
tokenId
clientId
clientSecret
applicationId
appId
webhookId
webhookUrl
secret
scope
scopes
```

---

# 17. OAuth Arguments

```text
provider
providerId
providerName
clientId
redirectUri
authorizationCode
code
accessToken
refreshToken
accountId
externalAccountId
```

---

# 18. Notification Arguments

```text
notificationId
userId
recipientId
channel
type
message
title
read
isRead
status
```

---

# 19. Messaging Arguments

```text
messageId
conversationId
threadId
channelId
senderId
recipientId
participantId
content
message
attachmentId
```

---

# 20. Search Arguments

```text
query
search
keyword
term
text
filter
filters
sort
sortBy
order
orderBy
```

---

# 21. Pagination Arguments

Very common in GraphQL APIs.

```text
first
last
after
before
offset
limit
page
pageSize
cursor
start
end
```

Example:

```graphql
query {
    users(
        first: 20
        after: "cursor123"
    ) {
        edges {
            node {
                id
                name
            }
        }
    }
}
```

---

# 22. Filtering Arguments

```text
filter
filters
where
status
statuses
type
types
category
categoryId
createdAt
updatedAt
from
to
min
max
```

---

# 23. Sorting Arguments

```text
sort
sortBy
sortOrder
order
orderBy
direction
```

Common values may include:

```text
ASC
DESC
ascending
descending
```

---

# 24. Date & Time Arguments

```text
date
startDate
endDate
startTime
endTime
createdAt
updatedAt
from
to
since
until
```

---

# 25. Boolean Arguments

GraphQL applications commonly use boolean arguments for feature/state changes.

```text
active
enabled
disabled
verified
approved
published
public
private
visible
deleted
archived
read
isActive
isAdmin
isVerified
isPublic
isPrivate
```

---

# 26. Common Mutation Input Arguments

Many mutations accept an input object instead of individual arguments.

Example:

```graphql
mutation {
    updateUser(
        id: "123"
        input: {
            name: "John"
            email: "john@example.com"
        }
    ) {
        id
        name
    }
}
```

Common input argument names:

```text
input
data
payload
attributes
fields
options
settings
config
configuration
```

---

# 27. Security-Interesting Arguments

During security testing, pay particular attention to arguments involving:

### Object Access

```text
id
userId
accountId
organizationId
orderId
documentId
postId
fileId
```

### Privilege Changes

```text
role
roleId
permission
permissionId
accessLevel
scope
```

### Sensitive Information

```text
password
token
apiKey
secret
clientSecret
accessToken
refreshToken
```

### Financial Operations

```text
amount
price
currency
paymentId
invoiceId
transactionId
```

### State Changes

```text
status
active
enabled
approved
verified
published
visibility
```

---

# 28. Argument Recon Workflow

When you discover an interesting field or mutation:

```text
Field / Mutation
        ↓
Arguments
        ↓
Argument Types
        ↓
Required / Optional
        ↓
Default Values
        ↓
Object Identifier
        ↓
Authorization
        ↓
Business Logic
```

Example:

```graphql
mutation {
    updateUser(
        userId: 123
        role: "admin"
    ) {
        id
        role
    }
}
```

Recon questions:

```text
Who can call updateUser?
        ↓
Can userId be changed?
        ↓
Can another user's ID be supplied?
        ↓
Can role be changed?
        ↓
Is role modification authorized?
        ↓
Does the server enforce the restriction?
```

---

# 29. Important Reminder

An argument name by itself does not indicate a vulnerability.

The security significance depends on:

* What the argument controls.
* What type it accepts.
* Whether it identifies an object.
* Whether it controls a privileged action.
* Whether the value is user-controlled.
* Whether server-side authorization is enforced.
* Whether changing the value produces an unauthorized effect.

Arguments are therefore one of the most important pieces of information to collect during GraphQL schema reconnaissance.
