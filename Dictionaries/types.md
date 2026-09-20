# GraphQL Type Dictionary

A collection of common GraphQL type and object names that may appear in real-world applications.

> These names are common naming patterns, not universal GraphQL specifications. Actual type names depend on the application's schema and implementation.

---

## 1. User & Account Types

```text
User
Account
Profile
UserProfile
Customer
Member
Admin
Administrator
UserAccount
UserSettings
UserPreferences
UserSession
Session
Identity
```

---

## 2. Authentication Types

```text
Auth
Authentication
Login
LoginResponse
LoginResult
AuthResponse
AuthResult
Session
SessionInfo
Token
AccessToken
RefreshToken
TokenResponse
Credentials
Verification
VerificationCode
EmailVerification
PhoneVerification
```

---

## 3. Authorization Types

```text
Role
Permission
Privilege
AccessControl
Authorization
Policy
PolicyRule
RolePermission
UserRole
PermissionSet
AccessRule
```

---

## 4. Admin Types

```text
AdminUser
AdminAccount
AdminProfile
AdminSettings
AdminAction
AdminActionResult
Moderation
ModerationAction
ModerationResult
AuditLog
AdminLog
SystemLog
```

---

## 5. Product & Catalog Types

```text
Product
ProductVariant
ProductOption
ProductAttribute
ProductCategory
Category
Subcategory
Brand
Catalog
CatalogItem
ProductImage
ProductMedia
ProductReview
ProductRating
Price
ProductPrice
Currency
```

---

## 6. Inventory Types

```text
Inventory
InventoryItem
Stock
StockItem
Warehouse
WarehouseItem
StockMovement
InventoryMovement
InventoryAdjustment
InventoryTransaction
```

---

## 7. Order Types

```text
Order
OrderItem
OrderLine
OrderStatus
OrderHistory
OrderEvent
Cart
CartItem
Checkout
CheckoutSession
Purchase
PurchaseItem
```

---

## 8. Payment Types

```text
Payment
PaymentMethod
PaymentIntent
PaymentTransaction
PaymentResult
PaymentStatus
Transaction
TransactionResult
Billing
BillingInfo
BillingAddress
PaymentDetails
```

---

## 9. Invoice & Subscription Types

```text
Invoice
InvoiceItem
InvoiceLine
Subscription
SubscriptionPlan
Plan
BillingPlan
SubscriptionItem
SubscriptionStatus
BillingCycle
```

---

## 10. Shipping & Delivery Types

```text
Shipment
ShipmentItem
ShippingAddress
ShippingMethod
ShippingRate
Delivery
DeliveryAddress
DeliveryMethod
Tracking
TrackingEvent
TrackingInfo
Carrier
```

---

## 11. Content & Blog Types

```text
Post
Article
BlogPost
Content
ContentItem
Page
Comment
CommentReply
Tag
Category
Author
Editor
Draft
Publication
Revision
```

---

## 12. Media & File Types

```text
File
FileUpload
FileMetadata
Media
MediaFile
Image
Video
Audio
Document
Attachment
Upload
Folder
Directory
StorageObject
```

---

## 13. Organization Types

```text
Organization
Company
Business
Workspace
Tenant
AccountOrganization
OrganizationMember
OrganizationSettings
OrganizationRole
OrganizationPermission
```

---

## 14. Team Types

```text
Team
TeamMember
TeamRole
TeamPermission
TeamSettings
TeamInvitation
Invitation
Membership
MemberRole
```

---

## 15. API & Developer Types

```text
ApiKey
APIKey
ApiToken
AccessKey
SecretKey
Developer
DeveloperAccount
Application
App
Client
ClientApplication
ApiClient
Webhook
WebhookEvent
WebhookDelivery
```

---

## 16. OAuth & External Account Types

```text
OAuthAccount
OAuthConnection
ConnectedAccount
ExternalAccount
SocialAccount
IdentityProvider
OAuthProvider
Provider
Integration
IntegrationAccount
```

---

## 17. Notification Types

```text
Notification
NotificationSettings
NotificationPreference
NotificationEvent
PushNotification
EmailNotification
SMSNotification
Alert
AlertSettings
```

---

## 18. Messaging & Chat Types

```text
Message
MessageThread
Conversation
Chat
ChatMessage
ChatRoom
Channel
Participant
ConversationMember
MessageAttachment
```

---

## 19. Social Types

```text
Friend
FriendRequest
Follower
Following
Follow
Relationship
UserRelationship
Block
BlockedUser
SocialProfile
```

---

## 20. Reporting & Analytics Types

```text
Report
ReportData
ReportResult
ReportFilter
Analytics
AnalyticsData
Metric
Metrics
Statistic
Statistics
Dashboard
DashboardData
Chart
DataExport
Export
ExportJob
```

---

## 21. Search Types

```text
SearchResult
SearchResults
SearchQuery
SearchFilter
SearchResponse
SearchSuggestion
SearchItem
Filter
FilterOption
Sort
SortOption
```

---

# Security-Interesting Types

During GraphQL reconnaissance, pay special attention to types related to:

## Identity

```text
User
Account
Profile
Identity
Session
Credentials
```

## Privileges

```text
Role
Permission
Privilege
AccessControl
Policy
```

## Administrative Functions

```text
Admin
AdminUser
AdminAction
Moderation
AuditLog
```

## Financial Data

```text
Payment
Transaction
Invoice
Billing
PaymentMethod
Subscription
```

## Sensitive Data

```text
Credentials
Token
AccessToken
RefreshToken
ApiKey
SecretKey
```

## Internal Systems

```text
InternalUser
InternalAccount
SystemConfig
SystemSettings
InternalSettings
DebugInfo
AuditLog
SystemLog
```

---

# Common Object Relationships

GraphQL types often reference other types through fields.

Example:

```graphql
type User {
    id: ID!
    name: String
    email: String
    orders: [Order]
    organization: Organization
    role: Role
}
```

Possible relationships:

```text
User
 ├── orders → Order
 ├── organization → Organization
 └── role → Role
```

Another example:

```graphql
type Order {
    id: ID!
    user: User
    items: [OrderItem]
    payment: Payment
    shippingAddress: ShippingAddress
}
```

This relationship structure is useful during security testing because one object may provide access to another object.

---

# Common Type Suffixes

GraphQL applications often use predictable naming patterns.

### Response Types

```text
UserResponse
UserResult
UserPayload
OrderResponse
OrderResult
MutationResponse
```

### Input Types

```text
UserInput
CreateUserInput
UpdateUserInput
OrderInput
ProductInput
FilterInput
```

### Connection Types

```text
UserConnection
OrderConnection
ProductConnection
UserEdge
OrderEdge
ProductEdge
```

### Pagination Types

```text
PageInfo
Pagination
PaginationInfo
Cursor
```

---

# Security Recon Workflow

When an interesting type is discovered:

```text
Type
 ↓
Fields
 ↓
Arguments
 ↓
Nested Types
 ↓
Object Identifiers
 ↓
Sensitive Fields
 ↓
Authorization
```

For example:

```text
User
 ↓
id
email
phone
role
permissions
orders
organization
```

Then investigate whether the current user is authorized to access each object and field.

---

# Important Reminder

A type name being present in the schema does not automatically indicate a vulnerability.

The important questions are:

* What fields does the type expose?
* Which arguments do those fields accept?
* Which objects can be accessed?
* Which identifiers are used?
* Which fields contain sensitive information?
* Does the application enforce object-level authorization?
* Does the application enforce field-level authorization?
* Are administrative or internal types accessible to unauthorized users?

Type discovery should therefore be treated as a starting point for deeper GraphQL security testing.
