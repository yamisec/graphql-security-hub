# GraphQL Mutation Dictionary

A collection of common GraphQL mutation names and naming patterns that may appear in real-world applications.

> These names are common patterns, not universal GraphQL specifications. Actual mutation names depend on the application's schema and implementation.

---

## 1. User & Account

```text
createUser
updateUser
deleteUser
createAccount
updateAccount
deleteAccount
activateAccount
deactivateAccount
enableUser
disableUser
verifyUser
unverifyUser
approveUser
rejectUser
suspendUser
unsuspendUser
restoreUser
```

---

## 2. Authentication

```text
login
logout
signIn
signOut
register
signup
refreshToken
revokeToken
verifyEmail
resendVerificationEmail
verifyPhone
resendVerificationCode
```

---

## 3. Password & Recovery

```text
changePassword
resetPassword
forgotPassword
requestPasswordReset
confirmPasswordReset
setPassword
updatePassword
unlockAccount
```

---

## 4. Roles & Permissions

```text
assignRole
removeRole
updateRole
createRole
deleteRole
addRole
removePermission
addPermission
updatePermission
createPermission
deletePermission
grantPermission
revokePermission
```

---

## 5. Admin & Moderation

```text
adminUpdateUser
adminDeleteUser
adminCreateUser
adminApproveUser
adminRejectUser
adminSuspendUser
adminUnsuspendUser
banUser
unbanUser
moderateUser
approveContent
rejectContent
deleteContent
restoreContent
```

---

## 6. Products

```text
createProduct
updateProduct
deleteProduct
publishProduct
unpublishProduct
archiveProduct
restoreProduct
duplicateProduct
updateProductPrice
updateProductInventory
```

---

## 7. Inventory

```text
createInventory
updateInventory
deleteInventory
adjustInventory
increaseStock
decreaseStock
reserveStock
releaseStock
restockProduct
```

---

## 8. Orders

```text
createOrder
updateOrder
cancelOrder
deleteOrder
confirmOrder
approveOrder
rejectOrder
completeOrder
refundOrder
duplicateOrder
```

---

## 9. Shipping & Delivery

```text
createShipment
updateShipment
cancelShipment
trackShipment
updateShippingAddress
createDelivery
updateDelivery
cancelDelivery
```

---

## 10. Payment

```text
createPayment
processPayment
authorizePayment
capturePayment
cancelPayment
refundPayment
voidPayment
retryPayment
verifyPayment
```

---

## 11. Payment Methods

```text
addPaymentMethod
updatePaymentMethod
deletePaymentMethod
setDefaultPaymentMethod
removePaymentMethod
verifyPaymentMethod
```

---

## 12. Subscription & Billing

```text
createSubscription
updateSubscription
cancelSubscription
pauseSubscription
resumeSubscription
upgradeSubscription
downgradeSubscription
renewSubscription
createInvoice
updateInvoice
deleteInvoice
payInvoice
voidInvoice
```

---

## 13. Coupons & Discounts

```text
createCoupon
updateCoupon
deleteCoupon
activateCoupon
deactivateCoupon
applyCoupon
removeCoupon
createDiscount
updateDiscount
deleteDiscount
```

---

## 14. Content & Blog

```text
createPost
updatePost
deletePost
publishPost
unpublishPost
archivePost
restorePost
createArticle
updateArticle
deleteArticle
publishArticle
```

---

## 15. Comments & Interactions

```text
createComment
updateComment
deleteComment
approveComment
rejectComment
likePost
unlikePost
likeComment
unlikeComment
bookmarkPost
removeBookmark
```

---

## 16. Media & Files

```text
uploadFile
deleteFile
updateFile
renameFile
moveFile
copyFile
createFolder
deleteFolder
updateMedia
deleteMedia
```

---

## 17. Organization & Company

```text
createOrganization
updateOrganization
deleteOrganization
archiveOrganization
restoreOrganization
inviteMember
removeMember
updateMember
transferOwnership
```

---

## 18. Team Management

```text
createTeam
updateTeam
deleteTeam
addTeamMember
removeTeamMember
updateTeamMember
inviteTeamMember
acceptTeamInvitation
rejectTeamInvitation
```

---

## 19. API Keys & Tokens

```text
createApiKey
updateApiKey
deleteApiKey
revokeApiKey
rotateApiKey
createAccessToken
revokeAccessToken
refreshAccessToken
```

---

## 20. OAuth & Connected Accounts

```text
connectAccount
disconnectAccount
linkAccount
unlinkAccount
authorizeConnection
revokeConnection
```

---

## 21. Notifications

```text
createNotification
markNotificationRead
markAllNotificationsRead
deleteNotification
clearNotifications
updateNotificationSettings
```

---

## 22. Messaging & Chat

```text
sendMessage
editMessage
deleteMessage
createConversation
deleteConversation
archiveConversation
restoreConversation
addParticipant
removeParticipant
```

---

## 23. Social & Relationships

```text
followUser
unfollowUser
blockUser
unblockUser
addFriend
removeFriend
acceptFriendRequest
rejectFriendRequest
sendFriendRequest
```

---

## 24. Data & Export

```text
exportData
exportUsers
exportOrders
exportReports
generateReport
downloadReport
deleteAccount
deleteUserData
```

---

## 25. Settings

```text
updateSettings
updateProfile
updatePreferences
updatePrivacySettings
updateNotificationSettings
updateSecuritySettings
```

---

# Security-Interesting Mutation Patterns

During GraphQL reconnaissance, pay particular attention to mutations involving:

### Account Control

```text
changePassword
resetPassword
deleteAccount
updateEmail
updatePhone
```

### Privilege Changes

```text
assignRole
updateRole
grantPermission
revokePermission
```

### Administrative Actions

```text
approveUser
suspendUser
banUser
restoreUser
deleteUser
```

### Sensitive Data

```text
exportData
exportUsers
generateReport
downloadReport
```

### Financial Operations

```text
refundPayment
cancelPayment
changeBilling
updatePaymentMethod
```

### Object Modification

```text
updateUser
updateOrder
updateProduct
updateOrganization
updateTeam
```

---

# Recon Notes

Mutation names alone do not prove that a vulnerability exists.

For each interesting mutation, investigate:

```text
Mutation
   ↓
Arguments
   ↓
Input Types
   ↓
Object Identifiers
   ↓
Return Type
   ↓
Authentication
   ↓
Authorization
   ↓
Business Logic
   ↓
Actual Effect
```

Important identifiers may include:

```text
id
userId
accountId
orderId
productId
organizationId
teamId
invoiceId
paymentId
```

---

# Important Reminder

A mutation being present in the schema does not automatically mean it is exploitable.

Security testing should determine:

* Who can call it.
* Which objects can be modified.
* Which fields can be changed.
* Whether authorization is enforced server-side.
* Whether the operation affects another user's data.
* Whether the operation performs a privileged action.
* Whether business logic restrictions can be bypassed.
