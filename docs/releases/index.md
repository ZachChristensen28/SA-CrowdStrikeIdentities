# Release notes

## [v1.0.0 <small>June 8, 2023</small>](https://github.com/ZachChristensen28/SA-CrowdStrike/releases/tag/v1.0.0){ target="blank" }

### Compatibility

Product | Version
--------- | -------
Splunk platform versions | 9.x, 8.x
Splunk Enterprise Security version | [7.x, 6.x](https://splunkbase.splunk.com/app/263){ target="blank" }
CrowdStrike Falcon Identity Protection Add-on | [>=1.0.1](https://splunkbase.splunk.com/app/6893){ target="blank" }

### What's Changed

- Initial release

**Full Changelog**: [v1.0.0](https://github.com/ZachChristensen28/SA-CrowdStrikeIdentities/commits/v1.0.0){ target="blank" }

## Known issues

Issue | Description | Solution | GitHub issue reference
----- | ----------- | -------- | ----------------------
Lookup file error | You may see the error `status="Lookup file error, unknown path or update time" name=crowdstrike_identities` | This error exists since the KVstore is being used opposed to a csv file and does not interfere with the functionality of lookup creation. | Issue [#2](https://github.com/ZachChristensen28/SA-CrowdStrikeIdentities/issues/2){ target="blank" }

 Issues or feature requests can be reported on the [SA-CrowdStrikeIdentities's Github page](https://github.com/ZachChristensen28/SA-CrowdStrikeIdentities/issues){ target="blank" }.
