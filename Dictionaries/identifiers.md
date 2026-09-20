# GraphQL Identifier Dictionary

A collection of common GraphQL identifiers used to reference users, accounts, organizations, resources, and internal objects.

These identifiers are useful during GraphQL reconnaissance, object-level authorization testing, IDOR testing, and understanding relationships between GraphQL objects.

---

## User & Account Identifiers

```text
id
userId
userID
user_id
accountId
accountID
account_id
profileId
profileID
profile_id
memberId
memberID
member_id
customerId
customerID
customer_id
clientId
clientID
client_id
ownerId
ownerID
owner_id
```

---

## Authentication & Identity

```text
sessionId
sessionID
session_id
loginId
loginID
login_id
identityId
identityID
identity_id
credentialId
credentialID
credential_id
authId
authID
auth_id
tokenId
tokenID
token_id
apiKeyId
apiKeyID
api_key_id
```

---

## Authorization & Role

```text
roleId
roleID
role_id
permissionId
permissionID
permission_id
privilegeId
privilegeID
privilege_id
groupId
groupID
group_id
accessId
accessID
access_id
policyId
policyID
policy_id
```

---

## Organization & Tenant

```text
organizationId
organizationID
organization_id
orgId
orgID
org_id
tenantId
tenantID
tenant_id
workspaceId
workspaceID
workspace_id
companyId
companyID
company_id
businessId
businessID
business_id
departmentId
departmentID
department_id
```

---

## Team & Membership

```text
teamId
teamID
team_id
memberId
memberID
member_id
membershipId
membershipID
membership_id
teamMemberId
teamMemberID
team_member_id
inviteId
inviteID
invite_id
```

---

## Product & Catalog

```text
productId
productID
product_id
itemId
itemID
item_id
sku
skuId
skuID
sku_id
variantId
variantID
variant_id
categoryId
categoryID
category_id
brandId
brandID
brand_id
catalogId
catalogID
catalog_id
```

---

## Inventory

```text
inventoryId
inventoryID
inventory_id
stockId
stockID
stock_id
warehouseId
warehouseID
warehouse_id
locationId
locationID
location_id
batchId
batchID
batch_id
serialId
serialID
serial_id
```

---

## Orders & Transactions

```text
orderId
orderID
order_id
transactionId
transactionID
transaction_id
purchaseId
purchaseID
purchase_id
cartId
cartID
cart_id
checkoutId
checkoutID
checkout_id
invoiceId
invoiceID
invoice_id
receiptId
receiptID
receipt_id
```

---

## Payment & Billing

```text
paymentId
paymentID
payment_id
paymentMethodId
paymentMethodID
payment_method_id
billingId
billingID
billing_id
billingAccountId
billingAccountID
billing_account_id
cardId
cardID
card_id
refundId
refundID
refund_id
payoutId
payoutID
payout_id
```

---

## Subscription

```text
subscriptionId
subscriptionID
subscription_id
planId
planID
plan_id
subscriptionPlanId
subscriptionPlanID
subscription_plan_id
invoiceId
invoiceID
invoice_id
renewalId
renewalID
renewal_id
```

---

## Content

```text
postId
postID
post_id
articleId
articleID
article_id
pageId
pageID
page_id
contentId
contentID
content_id
documentId
documentID
document_id
storyId
storyID
story_id
draftId
draftID
draft_id
```

---

## Comments & Social

```text
commentId
commentID
comment_id
replyId
replyID
reply_id
messageId
messageID
message_id
conversationId
conversationID
conversation_id
threadId
threadID
thread_id
notificationId
notificationID
notification_id
```

---

## Media & Files

```text
fileId
fileID
file_id
mediaId
mediaID
media_id
imageId
imageID
image_id
videoId
videoID
video_id
attachmentId
attachmentID
attachment_id
uploadId
uploadID
upload_id
folderId
folderID
folder_id
```

---

## API & Developer Resources

```text
apiId
apiID
api_id
apiKeyId
apiKeyID
api_key_id
applicationId
applicationID
application_id
appId
appID
app_id
projectId
projectID
project_id
environmentId
environmentID
environment_id
integrationId
integrationID
integration_id
webhookId
webhookID
webhook_id
```

---

## OAuth & External Identity

```text
oauthId
oauthID
oauth_id
providerId
providerID
provider_id
clientId
clientID
client_id
connectionId
connectionID
connection_id
externalId
externalID
external_id
identityId
identityID
identity_id
```

---

## Security & Audit

```text
auditId
auditID
audit_id
eventId
eventID
event_id
logId
logID
log_id
securityEventId
securityEventID
security_event_id
accessLogId
accessLogID
access_log_id
requestId
requestID
request_id
```

---

# Identifier Patterns

GraphQL applications may expose identifiers using different naming conventions.

### camelCase

```text
userId
accountId
orderId
organizationId
```

### snake_case

```text
user_id
account_id
order_id
organization_id
```

### ID suffix

```text
userID
accountID
orderID
```

### Generic ID

```text
id
```

### Reference-style identifiers

```text
userRef
accountRef
orderRef
resourceRef
objectRef
```

### UUID-style identifiers

```text
userUuid
accountUuid
resourceUuid
```

---

# Security-Interesting Identifiers

During authorization testing, prioritize identifiers that represent ownership or access boundaries.

```text
userId
accountId
ownerId
customerId
memberId
organizationId
tenantId
workspaceId
projectId
orderId
invoiceId
paymentId
subscriptionId
postId
documentId
fileId
messageId
conversationId
teamId
roleId
permissionId
apiKeyId
```

These can be especially interesting when changing the identifier changes which object is returned or modified.

---

# Object-Level Authorization Testing

Suppose a query accepts:

```graphql
query {
  user(id: "1001") {
    id
    email
    profile
  }
}
```

The identifier is:

```text
id
```

A security tester can determine whether the application properly checks ownership/authorization when the identifier refers to another user's object.

Common identifier substitution patterns:

```text
1001
1002
1003
```

or:

```text
"user-1001"
"user-1002"
"user-1003"
```

or UUID-style identifiers:

```text
"user-uuid-1"
"user-uuid-2"
```

The important point is not the identifier format itself.

The important question is:

> **Does changing the object identifier cause the server to return or modify an object that the current user is not authorized to access?**

---

# Mutation Identifier Testing

Identifiers can also appear inside mutations.

Example:

```graphql
mutation {
  updateUser(
    userId: "1002"
    email: "test@example.com"
  ) {
    id
    email
  }
}
```

Potentially security-relevant identifiers:

```text
userId
accountId
organizationId
orderId
invoiceId
paymentId
subscriptionId
postId
documentId
fileId
```

For authorized testing, determine whether the backend verifies that the authenticated user has permission to modify the referenced object.

---

# Nested Identifier Testing

Identifiers may appear inside nested input objects.

Example:

```graphql
mutation {
  updateOrder(
    input: {
      orderId: "1002"
      customerId: "2002"
    }
  ) {
    id
    status
  }
}
```

Important nested identifiers:

```text
orderId
customerId
userId
accountId
organizationId
```

When multiple identifiers exist in the same request, determine which identifier actually controls object ownership and which ones are merely informational.

---

# Relationship Identifiers

GraphQL commonly represents relationships between objects using identifiers.

Example:

```text
userId
organizationId
teamId
projectId
ownerId
parentId
```

Example relationship:

```text
User
 ├── organizationId
 ├── teamId
 └── projectId
```

These relationships can help map the application's authorization boundaries during reconnaissance.

---

# Parent / Child Identifiers

Common hierarchical identifiers:

```text
parentId
childId
parentOrganizationId
parentAccountId
rootId
folderId
containerId
resourceId
```

These can reveal how resources are organized.

For example:

```text
organizationId
    ↓
projectId
    ↓
documentId
    ↓
fileId
```

Understanding this relationship can help identify which object-level authorization checks should exist.

---

# Internal / Administrative Identifiers

Potentially interesting internal identifiers include:

```text
adminId
staffId
employeeId
moderatorId
operatorId
internalUserId
serviceId
serviceAccountId
systemId
backendId
```

These should be treated as reconnaissance targets rather than proof of a vulnerability.

---

# Identifier Discovery Workflow

A practical workflow:

```text
1. Discover GraphQL endpoint
        ↓
2. Check introspection
        ↓
3. Enumerate Query / Mutation fields
        ↓
4. Enumerate arguments
        ↓
5. Identify ID-like arguments
        ↓
6. Identify returned object types
        ↓
7. Map object relationships
        ↓
8. Identify ownership boundaries
        ↓
9. Test authorization with controlled identifiers
        ↓
10. Verify impact
```

---

# What To Look For

When reviewing a GraphQL schema, search for:

```text
id
*Id
*ID
*_id
*Uuid
*UUID
*Ref
*RefId
*Key
```

Examples:

```text
userId
accountId
resourceId
ownerId
tenantId
projectId
documentId
externalId
resourceUuid
```

---

# Identifier Recon Checklist

```text
[ ] Find generic id fields
[ ] Find *Id arguments
[ ] Find *ID arguments
[ ] Find *_id arguments
[ ] Find UUID-style identifiers
[ ] Find reference-style identifiers
[ ] Identify owner identifiers
[ ] Identify tenant identifiers
[ ] Identify organization identifiers
[ ] Identify parent/child relationships
[ ] Identify resource identifiers
[ ] Identify identifiers inside input objects
[ ] Identify identifiers accepted by mutations
[ ] Map identifiers to returned object types
[ ] Map identifiers to authorization boundaries
```

---

# Security Mindset

An identifier by itself is not a vulnerability.

The security question is:

> **Does the server properly authorize access to the object referenced by that identifier?**

For GraphQL security testing, identifiers are mainly useful for discovering and testing **object-level authorization boundaries**, **resource ownership**, and **relationships between GraphQL objects**.
