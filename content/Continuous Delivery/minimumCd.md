---
title: Minimum CD
tags:
 - CD
---

See MinimumCd.org(https://minimumcd.org)

%%{init: {'securityLevel': 'loose', 'theme': 'base', 'themeVariables': { 'primaryColor': '#327fa8', 'primaryTextColor': '#f0f3f5'}}}%%

{{<mermaid align="center">}}

%%{init: { 'theme': 'base', 'themeVariables': { 'primaryColor': '#327fa8', 'primaryTextColor': '#f0f3f5'}}}%%
graph TB
%%{config: { 'fontFamily': 'Menlo', 'fontSize': 8, 'fontWeight': 400} }%%
CI[[Continuous Integration]]
CD(Continuous Delivery)
TBD[[Trunk-based<br>Development]]

CD ==> CI
CI ==> TBD
CI --> CIA(Integrates to trunk<br>at least daily)
CI --> CIB(Automated testing<br>before merge to trunk)
CI --> CIC(Tested with other<br>work automatically<br>on merge)
CI --> CID(All feature work<br>stops when<br>build is red)
CI --> CIE(New work does<br>not break<br>delivered work)

TBD --> BRANCH{Use branches?}
BRANCH -- No --> DTT(Push to Trunk)
BRANCH -- Yes --> SLFB(Branches)
SLFB --> A(Originate from trunk<br>Re-integrate to trunk)
SLFB --> C(Short-lived<br>Removed after merge)

{{< /mermaid >}}

