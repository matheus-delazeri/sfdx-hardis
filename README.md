# SFDX Hardis - Fork

This fork aims to provide the capability of exporting Flows to PDF using the [md-to-pdf](https://www.npmjs.com/package/md-to-pdf) package.

- [Installation](#installation)
- [Dependencies](#dependencies)


## Installation

1. Install Node.js ([recommended version](https://nodejs.org/en/))
2. Install typescript by running `npm install typescript --global`
3. Install yarn by running `npm install yarn --global`
4. Install Salesforce DX by running `npm install @salesforce/cli --global` command line
5. Clone this repo
6. At the root of the repository:
  - Run `yarn` to install dependencies
  - Run `sf plugins link` to link the local sfdx-hardis to SFDX CLI
  - Run `tsc` to compile

## Dependencies

**sfdx-hardis** partially relies on the following SFDX Open-Source packages

- [Salesforce Data Move Utility](https://github.com/forcedotcom/SFDX-Data-Move-Utility)
- [SFDX Git Delta](https://github.com/scolladon/sfdx-git-delta)
- [Texei Sfdx Plugin](https://github.com/texei/texei-sfdx-plugin)
