For ATF – Eligible but Not Interested
TC01 – Verify ‘ATF – Eligible but Not Interested’ list view appears in dropdown
TC02 – Verify list view shows only ATF opportunities where Eligibility = Eligible
TC03 – Verify list view filters opportunities with Status = ‘Lead Submitted’
TC04 – Verify non-ATF opportunities do NOT appear in ‘Eligible but Not Interested’
TC05 – Verify opportunities with other statuses do NOT appear in this list view
For ATF – Progress to Application
TC06 – Verify ‘ATF – Progress to Application’ list view appears in dropdown
TC07 – Verify list view shows only ATF opportunities
TC08 – Verify list view filters opportunities with Status = ‘Identified’
TC09 – Verify list view includes only opportunities where CreditApplicationID = NULL
TC10 – Verify opportunities with CreditApplicationID populated do NOT appear
TC11 – Verify non-ATF opportunities do NOT appear in this list view
Generic List View Behaviour
TC12 – Verify list views load correct columns as defined
TC13 – Verify user permissions allow viewing ATF list views
TC14 – Verify list view records update dynamically when status or eligibility changes
TC15 – Verify sorting, actions, and filters work on each list view


✅ List View Availability
TC01 – Verify Decisioning list views appear in the Credit Application list view dropdown
TC02 – Verify list view names match requirement: ATF App Accept, ATF App Refer, ATF App Decline
✅ Decisioning – Pass
TC03 – Verify ‘Decisioning – Pass’ list view shows Credit Applications where Auto_Decision_Overall__c = ‘Pass’
TC04 – Verify Credit Applications with other decision values do NOT appear in ‘Decisioning – Pass’
✅ Decisioning – Refer
TC05 – Verify ‘Decisioning – Refer’ list view shows Credit Applications where Auto_Decision_Overall__c = ‘Refer’
TC06 – Verify Credit Applications with decision values ≠ ‘Refer’ do NOT appear in ‘Decisioning – Refer’
✅ Decisioning – Decline
TC07 – Verify ‘Decisioning – Decline’ list view shows only records where Auto_Decision_Overall__c = ‘Decline’
TC08 – Verify Credit Applications with other values do NOT appear in ‘Decisioning – Decline’
✅ General / Behaviour
TC09 – Verify list view columns match the configuration for ATF decisioning
TC10 – Verify list views refresh correctly when Auto_Decision_Overall__c is updated
TC11 – Verify only authorized users can view ATF decisioning list views
TC12 – Verify filtering accuracy when multiple Credit Applications exist



