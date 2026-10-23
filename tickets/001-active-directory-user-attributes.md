# Ticket 001: Active Directory User Attributes Troubleshooting

**Environment:** SysDesks ticketing simulation  
**Category:** Identity > User Attributes 
**Tier:** Tier 1  
**Status:** Resolved

## 1. Reported Issue
The user’s office location and phone extension reflected their previous desk instead of their current desk.

## 2. Troubleshooting Steps
1. Referenced the user’s account in the Active Directory.
2. Updated the “Location” field to the user’s current location.
3. Verified that the user’s office location and phone extension correctly reflected their current desk.

## 3. Root Cause
The user’s location was not updated to their current office on the Active Directory account. 

## 4. Resolution
Updated the user’s office location attribute in Active Directory to reflect the new location.

## 5. Verification
Verified that the user’s office location and phone extension reflected their current desk information. 
## 6. Skills Demonstrated
- Active Directory fundamentals
- User account attribute management
- Identity and directory services 
- Data accuracy and verification

## 7. Lessons Learned
User directory information should be reviewed and kept up-to-date when employees change desks or office locations. Verifying the displayed information after an update helps ensure that account records accurately reflect the user’s current details.

---
*This ticket was completed in a simulated IT support environment and does not represent production IT experience.*
