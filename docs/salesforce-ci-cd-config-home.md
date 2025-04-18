---
title: Configure a Salesforce CI/CD Project using sfdx-hardis
description: Learn how to configure your Salesforce CI/CD project so it works easily with VsCode SFDX Hardis
---
<!-- markdownlint-disable MD013 -->

- New task Options(#new-task-options)
- [package.xml](#packagexml)
  * [Overwrite Management](#overwrite-management)
  * [Delta deployments](#delta-deployments)
- [destructiveChanges.xml](#destructivechangesxml)
- [Automated sources cleaning](#automated-sources-cleaning)
- [Source retrieve issues](#source-retrieve-issues)
- [All configuration properties](#all-configuration-properties)

## New task options

Look at all the [Overwrite properties of new task command](https://sfdx-hardis.cloudity.com/hardis/work/new/) to define the appropriate values of your project.

## package.xml

A Salesforce CI/CD repository contains a file **manifest/package.xml**.

- It contains **all metadatas** that will be **deployed** by the **CI server**.

- It is **automatically updated** when [preparing merge requests](salesforce-ci-cd-publish-task.md#prepare-merge-request) by command [hardis:work:save](https://sfdx-hardis.cloudity.com/hardis/work/save/)

### Overwrite Management

- It is highly recommended to [**configure overwrite management**](salesforce-ci-cd-config-overwrite.md), to **avoid to overwrite metadatas that are maintained directly in production on purpose**
  - Dashboards
  - Reports
  - Remote site settings
  - Named credentials
  - ...

  _See [Overwrite management configuration documentation](salesforce-ci-cd-config-overwrite.md)_

### Delta deployments

- You can also use [**delta deployments**](salesforce-ci-cd-config-delta-deployment.md) if your project is big and you have performances issues.

### Source retrieve issues

Handle cases when force:source:pull does not retrieve every updated source.

_[See how to force the retrieve of named sources](salesforce-ci-cd-retrieve.md)_

___

## destructiveChanges.xml

A Salesforce CI/CD repository contains a file **manifest/destructiveChanges.xml**.

- It contains **all metadatas** that will be **deleted** by the **CI server**.

- It is **automatically updated** when [preparing merge requests](salesforce-ci-cd-publish-task.md#prepare-merge-request) by command [hardis:work:save](https://sfdx-hardis.cloudity.com/hardis/work/save/)

___

## Automated sources cleaning

You can configure automated cleaning of sources before creating merge requests, using command [hardis:work:save](https://sfdx-hardis.cloudity.com/hardis/work/save/)

Those cleanings can be:

- Deletion of sources existing in `destructiveChanges.xml`
- Remove from Profiles elements that are existing in Permission Sets, like Objects access configuration.
- etc ...

  _See [Overwrite cleaning configuration documentation](salesforce-ci-cd-config-cleaning.md)_

___

## All configuration properties

**.sfdx-hardis.yml** allows to make your project highly configuration. Have a look at its [list of configuration properties](schema/sfdx-hardis-json-schema-parameters.html) !
