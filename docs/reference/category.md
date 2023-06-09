# Category

## Default category field mapping

Mapped Field | CrowdStrike Event Field | Example value
------------ | ----------------------- | -------------
account_control | `accounts{}.userAccountControl` | 512
archived | `archived` | false
domain | `accounts{}.domain` | zachthesplunker.com
enabled | `accounts{}.enabled` | true
ou | `accounts{}.ou` | zachthesplunker.local/dev/users
pass_last_updated | `accounts{}.passwordAttributes.lastChange` | 2021-10-11t16:46:56.000z
risk_factors | `riskFactors{}.type` | stale_account,weak_password_policy
risk_score | `riskScore` | 0.43
risk_score_severity | `riskScoreSeverity` | normal
roles | `roles{}.type` | humanuseraccountrole,localadmin
splunk_last_updated | n/a | 08/26/22 18:54:42 MDT
title | `accounts{}.title` | splunker
watched | `watched` | true

### Full example of category value

```yaml
account_control: 512
archived: false
domain: zachthesplunker.com
enabled: true
gen: sa-crowdstrike
ou: zachthesplunker.local/dev/users
pass_last_updated: 2021-10-11t16:46:56.000z
risk_factors: stale_account,weak_password_policy
risk_score: 0.43
risk_score_severity: normal
roles: humanuseraccountrole
splunk_last_updated: 06/08/23 22:43:40 mdt
title: Splunker
watched: true
```
