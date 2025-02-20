---
title: Cloudflare Setup
meta_desc: This page provides an overview on how to configure the Pulumi Cloudflare Provider.
layout: installation
---

The Pulumi Cloudflare provider uses the Cloudflare SDK to manage resources.

> Pulumi relies on the Cloudflare SDK to authenticate requests from your computer to Cloudflare. Your credentials are never sent
> to pulumi.com.

### Configuring The Provider

Once obtained, there are two ways to communicate your configuration parameters to Pulumi:

1. Set the environment variable `CLOUDFLARE_API_TOKEN` (or the legacy `CLOUDFLARE_EMAIL` and `CLOUDFLARE_API_KEY`):

    ```bash
    $ export CLOUDFLARE_API_TOKEN=YYYYYY
    # Legacy
    $ export CLOUDFLARE_EMAIL=XXXXXX
    $ export CLOUDFLARE_API_KEY=YYYYYY
    ```

2. If you prefer that they be stored alongside your Pulumi stack for easy multi-user access:

    ```bash
    $ pulumi config set cloudflare:apiToken
    # Legacy
    $ pulumi config set cloudflare:email XXXXXX
    $ pulumi config set cloudflare:apiKey YYYYYY --secret
    ```

A full set of configuration parameters can be found listed on the [Project README](https://github.com/pulumi/pulumi-cloudflare/blob/master/README.md).
