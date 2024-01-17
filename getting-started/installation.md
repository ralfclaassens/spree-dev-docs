# Installation

## Self-hosted vs SaaS

Before you proceed we would like to remind you that we also offer Software as a Service platform called [Vendo](https://getvendo.com/?utm_source=spree_docs) which is essentialy Spree in the cloud, with [additional features](https://spreecommerce.org/spree-as-a-service/), global CDN, pre-built integrations without hosting headaches.&#x20;

![Vendo - Spree as a Service offerring](<https://uploads-ssl.webflow.com/6230c485f2c32ea1b0daa438/62386b96518cdcbe111f134a_OG%20Image%20(2).png>)

With [Vendo](https://getvendo.com/?utm_source=spree_docs), you just need to sign up and focus on your brand and storefront experience. The rest (hosting, maintenance, security, scaling) is handled by us.

## Prerequisites

Before proceeding make sure you have [Docker Desktop](https://docs.docker.com/get-docker/) installed on your system. This is fairly straightforward but differs depending on which operating system you use.

If you would like to add Spree to your existing Ruby on Rails application, please [follow this guide instead](../advanced/existing_app_tutorial.md) (for advanced users).

### Windows

Windows users will need to [install the Linux subsystem](https://docs.microsoft.com/en-us/windows/wsl/install-win10) to proceed.

## Installation

### Installation using Spree CLI

For the instructions on how to setup Spree with a dedicated CLI tool go to [this](../cli/getting-started-with-spree-cli.md) page.

### Manual installation

1. Download [Spree Starter](https://github.com/spree/spree_starter/archive/main.zip)
2. Unzip it
3. Rename `spree_starter-main` directory as you please
4. Run `bin/setup-docker` in said directory
5. Wait for the commands to execute (it can take around 2-3 minutes)
6. Run `bin/start-docker` to run the webserver

## Hello, Spree Commerce

You now have a functional Spree application after running only a few commands!

To stop the webserver, hit `Ctrl-C` in the terminal window where it's running.&#x20;

### Connecting to the API

Your API server is up and running.[ Download our Open API doc](https://raw.githubusercontent.com/spree/spree/master/api/docs/v2/storefront/index.yaml) and [import it to Postman](https://learning.postman.com/docs/integrations/available-integrations/working-with-openAPI/) to start playing around. Your backend server URL is `http://localhost:4000` so to grab the Products List you can use:

```bash
curl --request GET \
  --url http://localhost:4000/api/v2/storefront/products \
  --header 'Content-Type: application/json'
```

We recommend checking out our [API reference](https://api.spreecommerce.org/) for more details.

### Logging Into the Admin Panel

The next thing you'll probably want to do is to log into the admin interface. Use your browser window to navigate to [http://localhost:4000/admin](http://localhost:4000/admin). You can log in with the username `spree@example.com` and password `spree123`.

Upon successful authentication, you should see the admin screen:

![](../.gitbook/assets/admin_panel_978-2x.jpg)

Feel free to explore some of the Admin Panel features that Spree has to offer and to verify that your installation is working properly.
