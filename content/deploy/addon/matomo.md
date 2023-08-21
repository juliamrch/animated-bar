---
title: Matomo
position: 10
shortdesc: This add-on provides a Matomo Analytics solution based on existing Clever Cloud services.
tags:
- addons
keywords:
- matomo
- web analytics
- google analytics
- privacy
- gdpr
---

Matomo is an open-source web analytics solution which gives you full ownership of your data. It's a [GDPR compliant](https://matomo.org/gdpr-analytics) alternative to Google Analytics. You can learn more about Matomo on [their website](https://matomo.org).

Matomo on Clever Cloud will allow your marketing team to effortlessly setup a tailored web analytics solution, that can be adjusted to your needs and workloads.

{{< image "/images/matomo/full-dashboard.png" "Matomo Dashboard" >}}

## How it works?

When you subscribe the Matomo add-on, we automatically setup a PHP instance based on the latest Matomo release. It comes with the required MySQL database and an optional Redis cache.

We have chosen to let you see and manage these companion add-ons in the Console so that you could adjust them to your needs. You can change their settings and use the Clever Cloud ability to migrate from an S flavored database or cache to an L or XL if required. You can also activate autoscalabity (horizontal and/or vertical scaling).

By default, Matomo on Clever Cloud comes with small sized add-ons: 
- PHP Nano
- MySQL XXS BigStorage
- Redis S

We've already integrated the Clever Cloud SSO, so you can login directly into your matomo instance from the Console, start to integrate your website, create different users. 

## Create Matomo add-on

### Web Console

1. Create a new add-on by clicking on the **Create...** dropdown in the sidebar and then **an add-on**.
2. Select the Matomo add-on.
3. You can skip linking the add-on to an application, it won't be needed.
4. Enter the name of your Matomo add-on and select the zone where you wish to deploy it.
5. It's done!

### CLI

1. Make sure you have clever-tools installed locally. Report to the [getting started]({{< ref `/reference/clever-tools/getting_started.md` >}}) guide if needed.
2. List the available plans and options for Matomo: `clever addon providers show Matomo`.
3. In your terminal, you can then run `clever addon create matomo <app-name> --region <region> --org <org>` where `app-name` is the name you want for your add-on, `region` deployment region, and `org` the organization ID the application will be created under.

Refer to the [documentation]({{< ref `/reference/clever-tools/create.md` >}}) for more details on application creation with Clever Tools

## Accessing the Matomo interface

Once you created your add-on, you should get to the dashboard and see a link named `Access Matomo`. Opening that link will redirect you to our SSO authentication.

{{< readfile `/content/partials/single-sign-on.md` >}}

## Configure your Matomo instance

Once you accessed your Matomo interface, we can start configuring it. A custom Clever Cloud configuration is automatically installed on your instance during the provisioning.

This configuration helps you taking advantage of optimizations by using a Redis cache by default. 

### Using your Matomo

If you're new with Matomo, you would probably want to read the Matomo's guides on [the official documentation](https://matomo.org/guides/).

## Customize your Matomo instance

Matomo can be customized following your needs with a multitude of plugins. You can go into `Settings` gear icon and then `Marketplace` to manage them. Ultimately, you can click Install on whatever plugin you could find accurate.

Plugins can be browsed from [Matomo own plugin repository](https://plugins.matomo.org/).

## Security and updates

The Matomo add-on is a fully managed application, you don't have to select a particular version. Still its receives updates for both features and security, that we will managed for you with continuously upgraded version over time.

After being updated, you Matomo add-on could need to be restarted.

## Plans

Matomo on Clever Cloud is the easiest way to set it up, but you can go further and adjust the flavour of your instance, database or cache. We provide different plans for PHP, MySQL and Redis.

### Matomo PHP Instances

Those are the plans of the PHP instance:

<script type="module" src="https://components.clever-cloud.com/load.js?version=7&components=cc-pricing-product.smart-runtime"></script>

<div>
<cc-smart-container context='{"productId": "php" }'>
  <cc-pricing-product mode="runtime" action="none">
    <div slot="head"></div>
  </cc-pricing-product>
</cc-smart-container>
</div>

### MySQL database

Those plans are the available MySQL databases:

{{< pricingAddon "mysql-addon" "[\"cpu\", \"memory\", \"disk-size\", \"connection-limit\", \"has-logs\", \"has-metrics\"]" >}}

### Redis cache

Those plans are the available Redis cache:

{{< pricingAddon "redis-addon" "[\"cpu\", \"max-db-size\", \"disk-size\", \"connection-limit\", \"has-logs\", \"has-metrics\", \"databases\"]" >}}
