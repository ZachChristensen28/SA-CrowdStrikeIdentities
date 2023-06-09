---
hide:
    - toc
---

# Identity Database Mapping

The following table describes how this add-on maps to the Identity Database.

> reference [Format an asset or identity in Splunk ES](https://docs.splunk.com/Documentation/ES/latest/Admin/Formatassetoridentitylist#Identity_lookup_header){ target="blank" }

ES Identity lookup field | [CrowdStrike Identity TA Fields](https://splunkbase.splunk.com/app/6893) | Example value | Multi-value allowed
--- | --- | --- | ---
identity | `accounts{}.samAccountName` + `accounts{}.upn` | zach@zachthesplunker.com\|zachthesplunker | true
first | `primaryDisplayName` | zach | false
email | `emailAddresses{}` | zach@ztsplunker.com | false
priority | see [Configure Priority](/configure/priority) | medium | false
bunit | `accounts{}.department` | finance | true
category | see [Category field reference](../category) | see [Category field reference](../category) | true