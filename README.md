# XDC Network Improvement Proposals (XIPs)

**Before you initiate a pull request**, please read the [XIP-1](https://xips.xdc.community/XIPS/xip-1) process document. Ideas should be thoroughly discussed on [xdc.dev](https://xdc.dev) first.

This repository tracks ongoing improvements to the XDC Network. It contains:

- The [XIP status page](https://xips.xdc.community/), tracking protocols for XDC Network clients and applications
- The [process document](https://xips.xdc.community/XIPS/xip-1) that governs how protocols are published here

For help *implementing* an XIP, please visit the [XIP Chat Discord Channel](https://discord.com/channels/1002620393032519790/1006951188886986822).

If you would like to become an XIP Editor, please check the [XIP Editor Handbook](https://www.xdc.community/docs/xip-editor-handbook/).

## Mission

The goal of the XIP project is to document standardized protocols for XDC Network clients and applications and to document them in a high quality and implementable way.

## Preferred Citation Format

The canonical URL for a XIP that has achieved draft status at any point is at https://xips.xdc.community/. For example, the canonical URL for XIP-1 is https://xips.xdc.community/XIPS/xip-1.

Please consider anything which is not published on https://xips.xdc.community/ as a working paper.

And please consider anything published at https://xips.xdc.community/ with a status of "draft" as an incomplete draft.

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
