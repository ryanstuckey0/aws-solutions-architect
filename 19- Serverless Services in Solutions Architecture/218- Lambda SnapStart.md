# 218- Lambda SnapStart
- Lambda feature that helps improve function performance up to 10x for functions running at java11 and up
- When enabled, the function is invoked from a pre-initialized state, meaning the code can start running right away
- Lambda will initialize function whenever you upload a new deployment, takes a snapshot of the memory and disk state, and then use those snapshots to invoke the function
- 