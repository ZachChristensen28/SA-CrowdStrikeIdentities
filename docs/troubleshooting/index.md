---
hide:
    - toc
    - navigation
---

# Troubleshooting

There can be many issues when setting up a new app/add-on in Splunk. Below highlights the most common issues with this Add-on. Don't see your issue? Submit a new issue on [Github](https://github.com/ZachChristensen28/SA-CrowdStrikeIdentities/issues){ target="blank" }.

Issue | Description | Solution
----- | ----------- | --------
Identity Database not populating with CrowdStrike Data | The identity database may show no CrowdStrike data if the initial search has not run to build the identity database or the default macro has not been updated. | Verify the default macro has the correct index definition (see [Update Default Macro](/quickstart/quickstart/#update-default-macro)). Also see [Force build](/quickstart/quickstart/#force-initial-build) to build the CrowdStrike identity lookup before the first scheduled run.
