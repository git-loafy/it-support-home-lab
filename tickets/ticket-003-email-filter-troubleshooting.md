# Ticket 003: Email Filter Troubleshooting

**Environment:** SysDesks ticketing simulation  
**Category:** Software > Email  
**Tier:** Tier 1  
**Status:** Resolved

## 1. Reported Issue
The user reported that most of their inbox messages appeared to be missing. The messages were not visible in the inbox or Deleted Items, raising concerns about potential email loss.

## 2. Troubleshooting Steps
1. Connected to the user's device through a remote session.
2. Opened the NorthMail email application.
3. Reviewed the active inbox filters.
4. Selected the "All" view to display messages hidden by the existing filter.

## 3. Root Cause
An applied email filter was limiting which messages appeared in the inbox.

## 4. Resolution
Changed the inbox view to "All," restoring visibility of the previously hidden messages without deleting or modifying the messages.

## 5. Verification
The user reviewed the inbox and confirmed that the expected messages were visible again.

## 6. Skills Demonstrated
- Remote troubleshooting
- Email application support
- Inbox filter and view configuration
- Root cause identification
- User communication and resolution verification

## 7. Lessons Learned
When messages appear to be missing, investigate inbox filters and view settings before assuming that messages have been deleted. Start with non-destructive troubleshooting steps to avoid unnecessary changes or potential data loss.

---
*This ticket was completed in a simulated IT support environment and does not represent production IT experience.*
