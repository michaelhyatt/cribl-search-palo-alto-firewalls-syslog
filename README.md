# Palo Alto Search dashboards (Syslog)
----

This pack contains the dashboards to visualise Palo Alto firewall Syslog data stored in Cribl Lake or external object stores, like S3. This pack supports the Syslog processed by `Cribl Pack for Palo Alto Networks Firewalls` pack and stored with minimal changes.

## About this Pack

This pack provides a good starting point to start visualising the data based on the type of data and can be further customised to suit your needs.


## Deployment
### Storing data for Palo Alto syslog sources
The pack follows the format and naming introduced by Stream `Cribl Pack for Palo Alto Networks Firewalls` pack. Ensure the data is stored as is paying attention the following fields:
* `type` field specifying the format of the data (`USERID`, `TRAFFIC`, `THREAT`, etc). In case of object stores, this field can be extracted from the path to optimise query performance. Modify the macro `syslogType` to change the `type` field name, if your S3 path expression contains this token, e.g. set it to `dir_palo_type` if your S3 path expression is `monashuni-cribl-syslog-palo-logs/typed/${_time:%Y}/${_time:%m}/${_time:%d}/${_time:%H}/${_time:%M}/${dir_palo_type}`. This will ensure the partition token is used instead of filtering the raw data.
* Update the `syslogDataset` macro with the name of the dataset containing the syslog data.


## Release Notes

### Version 0.0.5 - 2025-12-08
Updated description.

### Version 0.0.4 - 2025-10-31
Added sample data with sample dashboards

### Version 0.0.3 - 2025-09-26
Initial Release

## Contributing to the Pack
To contribute to this Pack, or to report any issues or enhancement requests, please connect with Michael Hyatt on [Cribl Community Slack](https://cribl-community.slack.com).

## Contact
To contact us please email mhyatt@cribl.io

## License
All publicly posted Packs must include a license that allows for use by the general public, such as Apache 2.0, MIT, or GNU.
(Most Packs use the Apache 2.0 license.)

This Pack uses the following license: [`Apache 2.0`](https://github.com/criblio/appscope/blob/master/LICENSE).