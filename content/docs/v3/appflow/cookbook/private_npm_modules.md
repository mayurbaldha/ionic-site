---
layout: fluid/pro_docs_base
category: pro-cookbook
id: pro-cookbook
title: Recipes for Appflow
body_class: 'pro-docs'
hide_header_search: true
dark_header: true
---

# How to use private NPM modules

Get an authentication token using the npm CLI:

```
$ npm token create --read-only
npm password:
┌────────────────┬──────────────────────────────────────┐
│ token          │ 1a583a54-5515-4058-a3c4-047e5f699d27 │
├────────────────┼──────────────────────────────────────┤
│ cidr_whitelist │                                      │
├────────────────┼──────────────────────────────────────┤
│ readonly       │ true                                 │
├────────────────┼──────────────────────────────────────┤
│ created        │ 2019-01-08T20:53:17.461Z             │
└────────────────┴──────────────────────────────────────┘
```

Configure an `NPM_TOKEN` secret in your Appflow environment using the generated token as value:

<img src="/img/docs/pro/cookbook/npm-token-secret.png" class="browser" />

Check in a `.npmrc` file in the root of your project directory with the following line:

```
//registry.npmjs.org/:_authToken=${NPM_TOKEN}
```
