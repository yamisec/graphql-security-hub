# GraphQL Field Dictionary

A collection of common GraphQL field names that may appear in real-world applications.

> Field names are application-specific. These are common naming patterns that can help during GraphQL schema reconnaissance and security testing.

---

# 1. Identity Fields

```text
id
uuid
userId
accountId
profileId
memberId
customerId
ownerId
createdBy
updatedBy
```

---

# 2. User Fields

```text
name
firstName
lastName
fullName
username
displayName
email
phone
mobile
avatar
profilePicture
photo
bio
description
dateOfBirth
gender
language
timezone
```

---

# 3. Account Fields

```text
accountId
accountType
accountStatus
status
state
createdAt
updatedAt
createdBy
updatedBy
lastLogin
lastActive
loginCount
```

---

# 4. Authentication Fields

```text
username
email
password
passwordHash
passwordResetToken
verificationToken
verificationCode
otp
session
sessionId
token
accessToken
refreshToken
idToken
authToken
```

> Sensitive authentication fields should receive particular attention during authorized security testing.

---

# 5. Authorization Fields

```text
role
roleId
roles
permission
permissionId
permissions
privilege
privileges
accessLevel
scope
scopes
isAdmin
isStaff
isSuperuser
isOwner
isModerator
```

---

# 6. Profile & Personal Information

```text
profile
profileId
address
street
city
state
country
postalCode
zipCode
location
latitude
longitude
website
company
jobTitle
occupation
```

---

# 7. Product Fields

```text
id
productId
name
title
description
price
cost
currency
sku
barcode
category
categoryId
brand
brandId
variant
variantId
status
visibility
image
images
url
```

---

# 8. Inventory Fields

```text
inventoryId
stock
stockLevel
quantity
availableQuantity
reservedQuantity
warehouseId
locationId
sku
restockLevel
inventoryStatus
```

---

# 9. Order Fields

```text
orderId
orderNumber
userId
customerId
items
total
subtotal
tax
discount
shippingCost
currency
status
paymentStatus
shippingStatus
createdAt
updatedAt
```

---

# 10. Payment Fields

```text
paymentId
paymentMethodId
transactionId
amount
currency
status
paymentStatus
paymentMethod
transaction
transactionStatus
billingAddress
paymentDetails
paidAt
refundedAt
```

---

# 11. Invoice & Billing Fields

```text
invoiceId
invoiceNumber
billingId
billingAddress
billingEmail
subtotal
tax
discount
total
amountDue
amountPaid
currency
status
dueDate
paidAt
```

---

# 12. Subscription Fields

```text
subscriptionId
planId
plan
status
subscriptionStatus
startDate
endDate
trialStart
trialEnd
renewalDate
cancelledAt
billingCycle
price
currency
```

---

# 13. Shipping & Delivery Fields

```text
shipmentId
trackingId
trackingNumber
carrier
carrierId
shippingAddress
deliveryAddress
shippingMethod
deliveryMethod
shippingCost
deliveryStatus
shippingStatus
estimatedDelivery
deliveredAt
```

---

# 14. Content Fields

```text
id
title
name
slug
description
content
body
text
excerpt
author
authorId
category
categoryId
tags
tagIds
status
visibility
published
publishedAt
createdAt
updatedAt
```

---

# 15. Comment Fields

```text
commentId
postId
articleId
authorId
parentCommentId
content
body
status
createdAt
updatedAt
replies
```

---

# 16. Media & File Fields

```text
fileId
fileName
filename
name
path
filePath
url
downloadUrl
uploadUrl
mimeType
contentType
size
extension
metadata
storageKey
bucket
folderId
```

---

# 17. Organization Fields

```text
organizationId
companyId
workspaceId
tenantId
name
slug
description
ownerId
members
memberCount
roles
permissions
settings
status
createdAt
updatedAt
```

---

# 18. Team Fields

```text
teamId
name
description
ownerId
members
memberCount
roles
permissions
settings
status
createdAt
updatedAt
```

---

# 19. API & Developer Fields

```text
apiKey
apiKeyId
accessKey
secretKey
token
accessToken
refreshToken
clientId
clientSecret
applicationId
appId
webhookUrl
webhookSecret
scope
scopes
```

---

# 20. OAuth & Connected Account Fields

```text
provider
providerId
providerName
externalId
externalAccountId
accessToken
refreshToken
token
expiresAt
scope
scopes
connectedAt
```

---

# 21. Notification Fields

```text
notificationId
recipientId
senderId
type
title
message
content
read
isRead
status
createdAt
readAt
```

---

# 22. Messaging & Chat Fields

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
attachments
sentAt
editedAt
deletedAt
```

---

# 23. Social Fields

```text
followerId
followingId
friendId
senderId
recipientId
status
relationship
followers
following
friends
blockedUsers
```

---

# 24. Audit & Security Fields

```text
auditLog
auditLogs
activityLog
activityLogs
securityLog
securityLogs
loginHistory
loginAttempts
ipAddress
userAgent
lastLogin
lastLoginAt
lastActivity
lastActivityAt
```

---

# 25. Internal & Administrative Fields

These fields may reveal information about internal application state or administrative privileges.

```text
admin
adminId
adminData
internalData
internalId
internalNotes
privateNotes
privateData
debug
debugInfo
systemInfo
systemConfig
configuration
settings
permissions
role
isAdmin
```

---

# 26. Sensitive Data Fields

During schema reconnaissance, pay particular attention to fields that may contain sensitive information.

### Credentials

```text
password
passwordHash
passwordResetToken
verificationToken
```

### Tokens

```text
token
accessToken
refreshToken
idToken
apiToken
sessionToken
```

### Secrets

```text
secret
secretKey
apiKey
clientSecret
webhookSecret
privateKey
```

### Personal Data

```text
email
phone
address
dateOfBirth
location
```

### Internal Data

```text
privateNotes
internalNotes
adminData
internalData
debugInfo
systemConfig
```

---

# 27. State & Boolean Fields

These fields commonly represent the state of an object or feature.

```text
active
enabled
disabled
verified
approved
published
visible
public
private
deleted
archived
locked
suspended
blocked
banned
read
completed
cancelled
```

Common prefixed variants:

```text
isActive
isEnabled
isVerified
isApproved
isPublished
isVisible
isPublic
isPrivate
isDeleted
isArchived
isLocked
isSuspended
isAdmin
```

---

# 28. Relationship Fields

GraphQL commonly exposes relationships between objects.

Example:

```graphql
type User {
    id: ID!
    name: String
    orders: [Order]
    organization: Organization
    role: Role
}
```

Common relationship fields:

```text
user
owner
author
creator
members
users
orders
products
items
organization
company
team
role
permissions
comments
posts
followers
following
friends
```

---

# 29. Pagination Fields

Common fields returned by connection-based GraphQL APIs:

```text
edges
nodes
pageInfo
totalCount
count
hasNextPage
hasPreviousPage
startCursor
endCursor
cursor
```

Example:

```graphql
users {
    edges {
        node {
            id
            name
        }
    }
    pageInfo {
        hasNextPage
        endCursor
    }
}
```

---

# 30. Common Metadata Fields

```text
createdAt
updatedAt
deletedAt
publishedAt
archivedAt
createdBy
updatedBy
deletedBy
version
revision
metadata
```

---

# 31. Security-Interesting Field Patterns

During GraphQL reconnaissance, prioritize fields related to:

### Identity

```text
id
userId
accountId
ownerId
```

### Authorization

```text
role
roles
permission
permissions
isAdmin
isOwner
accessLevel
scope
```

### Credentials

```text
password
passwordHash
token
accessToken
refreshToken
```

### Secrets

```text
apiKey
secret
secretKey
clientSecret
privateKey
```

### Internal Information

```text
privateNotes
internalNotes
adminData
internalData
debugInfo
systemConfig
```

### Financial Information

```text
amount
balance
price
cost
paymentDetails
transaction
billing
```

---

# 32. Field Recon Workflow

When an interesting type is discovered:

```text
Type
 ↓
Fields
 ↓
Sensitive Fields
 ↓
Nested Objects
 ↓
Object Identifiers
 ↓
Authorization
 ↓
Actual Response
```

Example:

```graphql
query {
    user(id: 123) {
        id
        name
        email
        role
        permissions
        privateNotes
        orders {
            id
            total
        }
    }
}
```

Recon questions:

```text
Which fields are exposed?
        ↓
Which fields contain sensitive data?
        ↓
Can the current user access them?
        ↓
Can another user's object be requested?
        ↓
Are nested objects authorized?
        ↓
Are privileged fields protected?
```

---

# Important Reminder

A field being present in the GraphQL schema does not automatically indicate a vulnerability.

The security significance depends on:

* What information the field exposes.
* Which object owns the field.
* Whether the field contains sensitive information.
* Whether the current user is authorized to access it.
* Whether nested objects enforce authorization.
* Whether administrative or internal fields are exposed.
* Whether the response reveals unnecessary information.

Field discovery should therefore be treated as a starting point for deeper object-level and field-level authorization testing.
