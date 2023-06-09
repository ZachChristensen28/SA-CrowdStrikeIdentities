# Priority Field

!!! info "To update the `priority` field modify the `CrowdStrike Identities Lookup - Gen` saved search. It is recommended to clone the default search before making changes (see [Clone Saved Search](../best-practice/clone-search))."

The priority field is very generic by default and should be updated to suite your environment. The following table describes how this field is set.

Type | Condition | Severity | Description
---- | --------- | -------- | -----------
RegEx\* | admin | `critical` | Any identity that has the keyword "admin."
boolean | true() | `medium` | catch-all. Remaining identities receive medium severity.

!!! note ""
    \*Regex Match is performed on the category field.

```python title="Default priority field definition"
priority=case(
    match(category, "admin"), "critical",
    true(), "medium"
    )
```
