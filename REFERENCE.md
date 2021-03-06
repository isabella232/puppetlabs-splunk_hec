# Reference

<!-- DO NOT EDIT: This document was generated by Puppet Strings -->

## Table of Contents

### Classes

* [`splunk_hec`](#splunk_hec): Simple class to manage your splunk_hec connectivity note if you manage enable_reports, it will default to puppetdb,splunk_hec if you wish to 

### Tasks

* [`bolt_apply`](#bolt_apply): This task submits the a bolt apply report (and other data) to Splunk's HEC
* [`bolt_result`](#bolt_result): This task submits a bolt task result to Splunk's HEC
* [`cleanup_tokens`](#cleanup_tokens): Revokes the tokens generated by the Splunk App Puppet Report Viewer

### Plans

* [`splunk_hec::apply_example`](#splunk_hecapply_example)
* [`splunk_hec::result_example`](#splunk_hecresult_example)

## Classes

### `splunk_hec`

Simple class to manage your splunk_hec connectivity
note if you manage enable_reports, it will default to puppetdb,splunk_hec
if you wish to add other reports, you can do so with the reports param
note that you can have the module automatically add the splunk_hec reports
processor by setting reports to '', the empty string.

#### Parameters

The following parameters are available in the `splunk_hec` class.

##### `url`

Data type: `String`



##### `token`

Data type: `String`



##### `collect_facts`

Data type: `Array`



Default value: `["dmi","disks","partitions","processors","networking"]`

##### `enable_reports`

Data type: `Boolean`



Default value: ``false``

##### `record_event`

Data type: `Boolean`



Default value: ``false``

##### `manage_routes`

Data type: `Boolean`



Default value: ``false``

##### `reports`

Data type: `String`



Default value: `"puppetdb,splunk_hec"`

##### `facts_terminus`

Data type: `String`



Default value: `"puppetdb"`

##### `facts_cache_terminus`

Data type: `String`



Default value: `"splunk_hec"`

##### `pe_console`

Data type: `Optional[String]`



Default value: ``undef``

##### `timeout`

Data type: `Optional[Integer]`



Default value: ``undef``

##### `ssl_ca`

Data type: `Optional[String]`



Default value: ``undef``

##### `token_summary`

Data type: `Optional[String]`



Default value: ``undef``

##### `token_facts`

Data type: `Optional[String]`



Default value: ``undef``

##### `token_metrics`

Data type: `Optional[String]`



Default value: ``undef``

##### `url_summary`

Data type: `Optional[String]`



Default value: ``undef``

##### `url_facts`

Data type: `Optional[String]`



Default value: ``undef``

##### `url_metrics`

Data type: `Optional[String]`



Default value: ``undef``

##### `include_logs_status`

Data type: `Optional[Array]`



Default value: ``undef``

##### `include_logs_catalog_failure`

Data type: `Optional[Boolean]`



Default value: ``false``

##### `include_logs_corrective_change`

Data type: `Optional[Boolean]`



Default value: ``false``

##### `include_resources_status`

Data type: `Optional[Array]`



Default value: ``undef``

##### `include_resources_corrective_change`

Data type: `Optional[Boolean]`



Default value: ``false``

## Tasks

### `bolt_apply`

This task submits the a bolt apply report (and other data) to Splunk's HEC

**Supports noop?** false

#### Parameters

##### `report`

Data type: `Hash`

A hash of the report, the bulk of this will be used for the splunk event

##### `facts`

Data type: `Hash`

A hash of facts, name => value

##### `host`

Data type: `Optional[String[1]]`

Target's Identifying name, will use clientcert from facts if not provided

##### `plan_guid`

Data type: `Optional[String[1]]`

A guid used to identify invocation of the plan (should change each run)

##### `plan_name`

Data type: `Optional[String[1]]`

The name of the plan being run (shouldn't change each run)

### `bolt_result`

This task submits a bolt task result to Splunk's HEC

**Supports noop?** false

#### Parameters

##### `result`

Data type: `Hash`

The individual result from a result set

### `cleanup_tokens`

Revokes the tokens generated by the Splunk App Puppet Report Viewer

**Supports noop?** false

#### Parameters

##### `username`

Data type: `String`

Username configured in Puppet Report Viewer

## Plans

### `splunk_hec::apply_example`

The splunk_hec::apply_example class.

#### Parameters

The following parameters are available in the `splunk_hec::apply_example` plan.

##### `plan_guid`

Data type: `Optional[String[1]]`



##### `plan_name`

Data type: `Optional[String[1]]`



### `splunk_hec::result_example`

The splunk_hec::result_example class.

