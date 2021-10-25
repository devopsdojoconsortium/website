---
title: Minimum CD
tags:
 - CD
---

See MinimumCd.org(https://minimumcd.org)

{{<mermaid align="left">}}

flowchart TD
TBD ==> CI
CI ==> CD
CD(Continuous Delivery)

subgraph CI
    subgraph "Continuous Integration" TD
        CIC(Tested with other work automatically on merge)
        CIA(Integrates to trunk at least daily)
        CIB(Automated testing before merge to trunk)
        CIE(New work does not break delivered work)
        CID(All feature work stops when build is red)

        CIx(CI) --- CIC
        CIC --- CIA
        CIA --- CIB
        CIB --- CIE
        CIE --- CID
    end
end

subgraph TBD
    subgraph "Trunk-based Development" TD
        BRANCH{Use branches?} -- No --- DTT(Push to Trunk)
        BRANCH -- Yes --- SLFB(Branches)
        SLFB --- A(Originate from trunk Re-integrate to trunk)
        SLFB --- C(Short-lived Removed after merge)
    end
end

{{</mermaid>}}