# Azure ARM Template Exercise
## Exercise 2 — Lessons Learned

### SKU Change Issue
- Never change SKU type (e.g. Standard_LRS → Standard_GRS) on an existing 
  storage account mid-exercise.
- Caused a `PendingTransactionAlreadyExists` error — Azure locks the account 
  when a geo-replication change is already pending.
- Resolution: Delete resource group and redeploy clean with consistent SKU.
  (Left unresolved intentionally — exercise objectives already met.)

### Rule Going Forward
- Always use `Standard_LRS` throughout an exercise unless SKU change is 
  the specific thing being tested.
  