---
title: Minimum CD
tags:
 - CD
---

See MinimumCd.org(https://minimumcd.org)

%%{init: { 'theme': 'base', 'themeVariables': { 'primaryColor': '#327fa8', 'primaryTextColor': '#f0f3f5'}}}%% flowchart TB %%{config: { 'fontFamily': 'Menlo', 'fontSize': 8, 'fontWeight': 400} }%% 

{{<mermaid align="left">}}

graph

CI[[Continuous Integration]] 
CD(Continuous Delivery) 
TBD[[Trunk-based Development]]

CD ==> CI CI ==> TBD CI --> CIA(Integrates to trunk at least daily) 
CI --> CIB(Automated testing before merge to trunk) 
CI --> CIC(Tested with other work automatically on merge) 
CI --> CID(All feature work stops when build is red) 
CI --> CIE(New work does not break delivered work)

TBD --> BRANCH{Use branches?} 
BRANCH -- No --> DTT(Push to Trunk) 
BRANCH -- Yes --> SLFB(Branches) SLFB --> A(Originate from trunk Re-integrate to trunk) 
SLFB --> C(Short-lived Removed after merge)

{{</mermaid>}}