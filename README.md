# XDC Network Improvement Proposals (XIPs)

**Before you initiate a pull request**, please read the [XIP-1](https://XIPs.ethereum.org/XIPS/XIP-1) process document. Ideas should be thoroughly discussed on [Ethereum Research](https://ethresear.ch/t/read-this-before-posting/8) or [Ethereum Magicians](https://ethereum-magicians.org/) first.

This repository tracks ongoing improvements to Ethereum. It contains:

- The [XIP status page](https://XIPs.ethereum.org), tracking protocols for Ethereum clients and applications
- The [process document](https://XIPs.ethereum.org/XIPS/XIP-1) that governs how protocols are published here

For help *implementing* an XIP, please visit [Ethereum Stack Exchange](https://ethereum.stackexchange.com).

If you would like to become an XIP Editor, please check [XIP-5069](./XIPS/XIP-5069.md).

## Mission

The goal of the XIP project is to document standardized protocols for Ethereum clients and applications and to document them in a high quality and implementable way.

## Preferred Citation Format

The canonical URL for a XIP that has achieved draft status at any point is at https://XIPs.ethereum.org/. For example, the canonical URL for XIP-1 is https://XIPs.ethereum.org/XIPS/XIP-1.

Please consider anything which is not published on https://XIPs.ethereum.org/ as a working paper.

And please consider anything published at https://XIPs.ethereum.org/ with a status of "draft" as an incomplete draft.

## Automerger

This repository contains an "auto merge" feature to ease the workload for XIP editors. Pull requests to any XIP will be auto-merged if the XIP's authors approve the PR on GitHub. This is handled by the [XIP-Bot](https://github.com/ethereum/XIP-Bot).

## Validation

Pull requests in this repository must pass automated validation checks:

* HTML formatting and broken links are [checked](https://github.com/ethereum/XIPs/blob/master/.travis-ci.sh) using [html-proofer](https://rubygems.org/gems/html-proofer).
* XIP front matter and formatting are [checked](https://github.com/ethereum/XIPs/blob/master/.github/workflows/auto-merge-bot.yml) using [XIP Validator](https://github.com/ethereum/XIPv).

It is possible to run the XIP validator locally:
```sh
cargo install XIPv
XIPv <INPUT FILE / DIRECTORY>
```

## Build the status page locally

### Install prerequisites

1. Open Terminal.

2. Check whether you have Ruby 2.1.0 or higher installed:

   ```sh
   ruby --version
   ```

3. If you don't have Ruby installed, install Ruby 2.1.0 or higher.

4. Install Bundler:

   ```sh
   gem install bundler
   ```

5. Install dependencies:

   ```sh
   bundle install
   ```

### Build your local Jekyll site

1. Bundle assets and start the server:

   ```sh
   bundle exec jekyll serve
   ```

2. Preview your local Jekyll site in your web browser at http://localhost:4000.

More information on Jekyll and GitHub pages [here](https://help.github.com/en/enterprise/2.14/user/articles/setting-up-your-github-pages-site-locally-with-jekyll).
