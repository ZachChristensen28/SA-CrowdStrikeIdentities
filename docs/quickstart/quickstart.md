# Quick Start

!!! warning "Important"
    This supporting add-on must be installed alongside Splunk Enterprise Security. Ensure the [prequisites](../prerequisites) have been completed before proceeding.

This add-on has a savedsearch and identity configuration input enabled by default.

## Overview

1. [Updated default macro](#update-default-macro).
1. [Force Initial Build](#force-initial-build).
1. [Enable identity correlation](#enable-identity-correlation).
1. <small>(optional)</small> [Disable existing identity sources](#disable-existing-identity-sources).
1. <small>(optional)</small> [Update default savedsearch schedule](#update-default-savedsearch-schedule).

## Update default macro

!!! danger "[Danger, Will Robinson](https://cultural-phenomenons.fandom.com/wiki/Danger,_Will_Robinson){ target=blank }"
    Failure to update the macro to the correct setting will cause no identities to be available in Splunk Enterprise Security.

Macro | Default | Description
----- | ------- | -----------
`sa_crowdstrike_identities_index` | index=crowdstrike | Index definition for CrowdStrike identity index.

### Update Macro Procedure

!!! note "Update the index definition to the correct index that contains the `crowdstrike:identities` sourcetype."

Perform **_one_** of the following:

1. <small>(recommended)</small> Update via Splunk ES [General Settings](#es-general-settings).
1. Update via [Macro Definition](#macro-definition).

#### ES General Settings

<small>option 1 (recommended option)</small>

1. <small>(In Splunk Enterprise Security)</small> Navigate to Configure > General > General Settings.
1. From the "App" dropdown select `SA-CrowdStrikeIdentities`.
1. Update the SA-CrowdStrikeIdentities Index definition and click "Save."

---

#### Macro Definition

<small>option 2</small>

1. Navigate to Settings > Advanced Search > Search Macros.
1. From the "App" dropdown choose `SA-CrowdStrikeIdentities`.
1. Set the "Owner" dropdown to `any`.
1. Click the macro named `sa_crowdstrike_identities_index` to update the index definition.

---

## Force Initial Build

The initial build of the CrowdStrike identities will not occur until the first scheduled runtime (see [Update default savedsearch schedule](#update-default-savedsearch-schedule)). To force the initial build perform the following:

1. Navigate to Settings > Searches, reports, and alerts.
1. Set the "App" dropdown to `SA-CrowdStrikeIdentities`.
1. Set the "Owner" dropdown to `All`.
1. Click "Run" under actions for the search `CrowdStrike Identities Lookup - Gen`.

!!! note
    The search will run in a new tab over the default time period of 60 minutes. Expand the time frame to a larger window if the number of identities in the last 60 minutes does not seem accurate. The default search is configured to run hourly to continually append new identities reported from CrowdStrike.

---

## Enable asset correlation

Confirm asset correlation has been setup in Enterprise Security.

1. Navigate to Enterprise Security > Configure > Data Enrichment > Asset and Identity Management.
1. Switch to the "Correlation Setup" tab.
1. Either enable for all sourcetypes <small>(Recommended)</small> or selectively by sourcetype.
    - If you choose to enable select sourcetypes, ensure the `stash` sourcetype is also selected so Notable events will be enriched with asset information.
1. Save.

---

## Disable existing identity sources

!!! info "optional"

It may be possible that you have existing Identity Lookups defined. If CrowdStrike is the main "source of truth" in your environment the existing lookups may no longer be needed.

---

## Update default savedsearch schedule

!!! info "optional"

The default saved search runs on the 29th minute of every hour to update and continually build the CrowdStrike identities. To update the default schedule perform the following steps:

1. Navigate to Settings > Searches, reports, and alerts.
1. Set the "App" dropdown to `SA-CrowdStrikeIdentities`.
1. Set the "Owner" dropdown to `All`.
1. Click "Edit" under actions for the search `CrowdStrike Identities Lookup - Gen`.
1. Click "Edit Schedule" and update the schedule and necessary.
