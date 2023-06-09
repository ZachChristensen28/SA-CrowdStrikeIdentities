---
hide:
    - toc
---
# All Configurations

Below is a table that list all configuration for this add-on.

Name | Type | Web Location | CLI Location\* | Description
---- | ---- | ------------ | ------------- | -----------
CrowdStrike Identities Lookup - Gen | Saved Search | Settings > Searches reports, and alerts | savedsearches.conf | Populates the lookup file `crowdstrike_identities`.
crowdstrike_identities | lookup | Settings > Lookups > Lookup definitions | transforms.conf | Lookup definition for the KVStore collection `crowdstrike_identities_collection`.
crowdstrike_identities_collection | KVStore collection | n/a\*\* | collections.conf | KVStore configuration.
sa_crowdstrike_identities_index | Search macro | Settings > Advanced Search > Search Macros | macros.conf | Index definition for the CrowdStrike index that contains the sourcetype `crowdstrike:identities`.
identity_manager://crowdstrike_identities| Identity lookup configuration | Enterprise Security > Configure > Data Enrichment > Asset and Identity Management > Identity Lookups | inputs.conf | Identity configuration lookup to load CrowdStrike Identities into the identity database.

> \*CLI locations are relative to `../default`. Any update to CLI configuration files should be done in the local directory.

!!! tip
    **If you have the [Splunk App for Lookup File Editing](https://splunkbase.splunk.com/app/263){ target="blank" }, the KVStore collection `crowdstrike_identities_collection` is viewable within the Web interface.
