# GraphQL Input Type Dictionary

A collection of common GraphQL input type names that may appear in real-world applications.

> Input type names are application-specific. These are common naming patterns that can help during GraphQL schema reconnaissance and security testing.


# 1. User & Account Input Types

```text
UserInput
CreateUserInput
UpdateUserInput
UserCreateInput
UserUpdateInput
AccountInput
CreateAccountInput
UpdateAccountInput
AccountCreateInput
AccountUpdateInput
ProfileInput
UpdateProfileInput
UserProfileInput
```


# 2. Authentication Input Types

```text
LoginInput
SignInInput
SignUpInput
RegisterInput
RegistrationInput
AuthenticationInput
AuthInput
CredentialsInput
LoginCredentialsInput
AuthCredentialsInput
SessionInput
```


# 3. Password & Recovery Input Types

```text
PasswordInput
ChangePasswordInput
UpdatePasswordInput
ResetPasswordInput
ForgotPasswordInput
PasswordResetInput
SetPasswordInput
ConfirmPasswordInput
VerificationInput
VerificationCodeInput
OTPInput
```

# 4. Authorization & Permission Input Types

```text
RoleInput
CreateRoleInput
UpdateRoleInput
PermissionInput
CreatePermissionInput
UpdatePermissionInput
PermissionSetInput
RolePermissionInput
AccessControlInput
AuthorizationInput
PolicyInput
PolicyRuleInput
```

# 5. Admin Input Types

```text
AdminInput
AdminUserInput
AdminActionInput
AdminUpdateUserInput
ModerationInput
ModerationActionInput
ApprovalInput
RejectionInput
BanUserInput
SuspendUserInput
```

# 6. Product Input Types

```text
ProductInput
CreateProductInput
UpdateProductInput
ProductCreateInput
ProductUpdateInput
ProductVariantInput
CreateProductVariantInput
UpdateProductVariantInput
ProductOptionInput
ProductAttributeInput
ProductPriceInput
```

# 7. Inventory Input Types

```text
InventoryInput
CreateInventoryInput
UpdateInventoryInput
InventoryItemInput
StockInput
StockAdjustmentInput
InventoryAdjustmentInput
StockMovementInput
WarehouseInput
WarehouseItemInput
```


# 8. Order Input Types

```text
OrderInput
CreateOrderInput
UpdateOrderInput
OrderItemInput
CreateOrderItemInput
UpdateOrderItemInput
CartInput
CartItemInput
CheckoutInput
CheckoutSessionInput
```

# 9. Payment Input Types

```text
PaymentInput
CreatePaymentInput
UpdatePaymentInput
PaymentMethodInput
CreatePaymentMethodInput
UpdatePaymentMethodInput
PaymentIntentInput
PaymentDetailsInput
TransactionInput
RefundInput
```

# 10. Billing & Invoice Input Types

```text
BillingInput
BillingInfoInput
BillingAddressInput
InvoiceInput
CreateInvoiceInput
UpdateInvoiceInput
InvoiceItemInput
InvoiceLineInput
BillingDetailsInput
```

# 11. Subscription Input Types

```text
SubscriptionInput
CreateSubscriptionInput
UpdateSubscriptionInput
CancelSubscriptionInput
SubscriptionPlanInput
PlanInput
CreatePlanInput
UpdatePlanInput
BillingCycleInput
```

# 12. Shipping & Delivery Input Types

```text
ShipmentInput
CreateShipmentInput
UpdateShipmentInput
ShippingAddressInput
ShippingMethodInput
DeliveryInput
CreateDeliveryInput
UpdateDeliveryInput
DeliveryMethodInput
TrackingInput
```

# 13. Content & Blog Input Types

```text
PostInput
CreatePostInput
UpdatePostInput
ArticleInput
CreateArticleInput
UpdateArticleInput
BlogPostInput
ContentInput
CreateContentInput
UpdateContentInput
PageInput
```

# 14. Comment Input Types

```text
CommentInput
CreateCommentInput
UpdateCommentInput
CommentCreateInput
CommentUpdateInput
ReplyInput
CreateReplyInput
```

# 15. Media & File Input Types

```text
FileInput
UploadInput
FileUploadInput
CreateFileInput
UpdateFileInput
FileMetadataInput
MediaInput
CreateMediaInput
UpdateMediaInput
AttachmentInput
FolderInput
```

# 16. Organization Input Types

```text
OrganizationInput
CreateOrganizationInput
UpdateOrganizationInput
CompanyInput
CreateCompanyInput
UpdateCompanyInput
WorkspaceInput
CreateWorkspaceInput
UpdateWorkspaceInput
TenantInput
OrganizationMemberInput
```

# 17. Team Input Types

```text
TeamInput
CreateTeamInput
UpdateTeamInput
TeamMemberInput
AddTeamMemberInput
UpdateTeamMemberInput
TeamRoleInput
TeamPermissionInput
TeamInvitationInput
InvitationInput
``

# 18. API & Developer Input Types

```text
ApiKeyInput
CreateApiKeyInput
UpdateApiKeyInput
ApiTokenInput
AccessTokenInput
TokenInput
ApplicationInput
CreateApplicationInput
UpdateApplicationInput
WebhookInput
CreateWebhookInput
UpdateWebhookInput
```

# 19. OAuth & Integration Input Types

```text
OAuthInput
OAuthAccountInput
OAuthConnectionInput
ConnectedAccountInput
ExternalAccountInput
IntegrationInput
CreateIntegrationInput
UpdateIntegrationInput
ProviderInput
```

# 20. Notification Input Types

```text
NotificationInput
CreateNotificationInput
UpdateNotificationInput
NotificationSettingsInput
NotificationPreferenceInput
NotificationFilterInput
AlertInput
```

# 21. Messaging & Chat Input Types

```text
MessageInput
SendMessageInput
CreateMessageInput
UpdateMessageInput
ConversationInput
CreateConversationInput
UpdateConversationInput
ChatInput
ChatMessageInput
ParticipantInput
```

# 22. Social Input Types

```text
FollowInput
FriendRequestInput
CreateFriendRequestInput
RelationshipInput
BlockUserInput
UnblockUserInput
UserRelationshipInput
```


# 23. Search Input Types

```text
SearchInput
SearchQueryInput
SearchFilterInput
SearchFiltersInput
SearchOptionsInput
SearchSortInput
FilterInput
SortInput
```


# 24. Pagination Input Types

```text
PaginationInput
PageInput
PageInfoInput
CursorInput
PaginationOptionsInput
ConnectionInput
```

Common fields inside these inputs may include:

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
```

# 25. Date & Range Input Types

```text
DateRangeInput
TimeRangeInput
DateFilterInput
DateRangeFilterInput
TimeRangeFilterInput
PeriodInput
RangeInput
```

Common fields:

```text
start
end
from
to
startDate
endDate
startTime
endTime
```

# 26. Filter Input Types

```text
FilterInput
FiltersInput
WhereInput
SearchFilterInput
ProductFilterInput
UserFilterInput
OrderFilterInput
DateFilterInput
StatusFilterInput
```

# 27. Sort Input Types

```text
SortInput
SortOrderInput
SortOptionsInput
OrderByInput
SortByInput
```

Common fields:

```text
field
fieldName
direction
order
sort
```

Common values:

```text
ASC
DESC
```

# 28. Settings Input Types

```text
SettingsInput
UpdateSettingsInput
UserSettingsInput
AccountSettingsInput
ProfileSettingsInput
PrivacySettingsInput
SecuritySettingsInput
NotificationSettingsInput
PreferencesInput
UserPreferencesInput
```


# 29. Export & Report Input Types

```text
ExportInput
ExportDataInput
ExportUsersInput
ExportOrdersInput
ReportInput
CreateReportInput
ReportFilterInput
ReportOptionsInput
GenerateReportInput
```

# 30. Common Generic Input Types

Many GraphQL applications use generic input names.

```text
Input
CreateInput
UpdateInput
DeleteInput
CreateObjectInput
UpdateObjectInput
DeleteObjectInput
ActionInput
OptionsInput
SettingsInput
ConfigInput
ConfigurationInput
PayloadInput
DataInput
AttributesInput
```


# 31. Security-Interesting Input Types

During schema reconnaissance, pay particular attention to input types related to:

### Account Modification

```text
UpdateUserInput
UpdateAccountInput
UpdateProfileInput
```

### Privilege Modification

```text
RoleInput
PermissionInput
UpdateRoleInput
UpdatePermissionInput
AccessControlInput
```

### Authentication

```text
LoginInput
CredentialsInput
PasswordInput
ResetPasswordInput
```

### Financial Operations

```text
PaymentInput
RefundInput
PaymentMethodInput
BillingInput
```

### Administrative Actions

```text
AdminActionInput
ModerationInput
ApprovalInput
SuspendUserInput
BanUserInput
```


# 32. Input Type Recon Workflow

When an interesting mutation is discovered:

```text
Mutation
   ↓
Arguments
   ↓
Input Type
   ↓
Input Fields
   ↓
Nested Input Types
   ↓
Object Identifiers
   ↓
Sensitive Fields
   ↓
Authorization
```

Example:

```graphql
mutation UpdateUser($input: UpdateUserInput!) {
    updateUser(input: $input) {
        id
        name
        role
    }
}
```

The next step is to inspect the input type:

```graphql
query {
    __type(name: "UpdateUserInput") {
        name
        inputFields {
            name
            type {
                kind
                name
                ofType {
                    kind
                    name
                }
            }
        }
    }
}
```

Possible result:

```text
UpdateUserInput
├── id
├── name
├── email
├── phone
└── role
```

This tells you what values the mutation accepts.


# 33. Nested Input Types

Input types can contain other input types.

Example:

```graphql
input UpdateUserInput {
    id: ID!
    profile: ProfileInput
    settings: UserSettingsInput
}
```

Relationship:

```text
UpdateUserInput
├── id
├── profile
│   └── ProfileInput
└── settings
    └── UserSettingsInput
```

Nested inputs are important because sensitive or privileged fields may exist deeper inside the input structure.


# Important Reminder

An input type being present in the schema does not automatically indicate a vulnerability.

The important questions are:

* What fields does the input type accept?
* Which fields are required?
* Which fields are optional?
* Are there nested input types?
* Does the input contain object identifiers?
* Does it contain role or permission fields?
* Does it contain sensitive values?
* Does the server authorize each requested change?
* Can a user modify fields that should be server-controlled?

Input type discovery should therefore be treated as a way to understand the application's mutation and data-modification attack surface.
