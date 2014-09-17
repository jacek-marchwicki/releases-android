Change Log
==========

## 0.7.18
 * Close Layer push channel (not GCM push) after a few seconds of being in the background; resume in foreground.

## 0.7.17
 * Fixed re-adding participant to conversation not alerting participant changes.

## 0.7.16
 * Created LayerException in place of error alerts with `int code, String message`.
 * LayerSyncListener has onSyncError for reporting LayerExceptions encountered during synchronization.
 * Corrected Conversation `lastMessage` bug.
 * Corrected alerting 'SESSION_NOT_FOUND' as an authentication error.

## 0.7.15
 * Deleting conversations and messages synchronizes faster.
 * Fixed error on synchronizing conversations from scratch that include deleted messages.

## 0.7.14
 * Reduced synchronization time.
 * Send PUSH broadcasts from both GCM and Layer connection.
 * Corrected intermittent NullPointerException on launch.

## 0.7.13
 * Removed LayerNotificationCallback; added new Intent broadcast with `com.layer.sdk.PUSH` action.

## 0.7.12
 * LayerClient.markMessageAsRead()
 * Message.getRecipientStatus() map acts like Message.getRecipientStatus(userId)

## 0.7.11
 * Message.sentAt and Message.receivedAt populated.
 * Recipient status map contains known recipients, conversation participants, and sender.
 * Do not return locally-deleted Conversations, Participants, and Messages prior to synchronization.
 
## 0.7.10
 * LayerClient takes a UUID instead of a String for its Layer App ID.
 * Listeners moved to new `com.layer.sdk.listeners` package.
 * Services and Receivers moved to new `com.layer.sdk.services` package.
 * LayerChange and LayerChangeEvent moved to new `com.layer.sdk.changes` package.

## 0.7.9
 * Fixed bug in synchronizing a conversation from scratch which had a member deleted.
 * Fixed proguard error on Session.
 * Bumped Google Cloud Messaging to 5.+

## 0.7.8
 * Fixed LayerClient-not-instantiated-in-main-thread bug.
 
## 0.7.7
 * Managed connection and notification states.
 * Notification callback.
 * getConversationsWithParticipants() bug fix.

## 0.7.6
 * GCM.
 * Notifications.
 * LayerNotificationCallback.
 * Improved sync notifications.
 * Corrected uncached notification bug.
