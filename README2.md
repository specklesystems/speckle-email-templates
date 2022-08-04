# speckle-email-templates

Uses the [MJML](https://mjml.io/) framework to build e-mail templates without dealing with a lot of the complexity that often arises out of doing so.

## Env setup

- Make sure you have `yarn 1.x` available globally (e.g. through corepack)
- Make sure you have `docker-compose`

## Development

Use VSCode and make sure you install the recommended MJML extension. Through this extension you can will get syntax highlighting in .mjml files and also the option to trigger a live preview right from the specific .mjml file.

Before development do `yarn env:up` to start the docker environment that serves a local file server. You'll need that to be able to see assets in the preview pane, cause it expects assets to be hosted somewhere and accessed through HTTP, not loaded from a relative path on your PC.

The file server is accessible at `localhost:3030`, assets are served from `/assets` and built templates from `/templates`.

## Building

Run `yarn build` to build everything. Run `yarn watch` to build in watch mode.

## Testing

### Sending out email template

You can configure the MJML VSCode extension to actually send out an email of your template. To do so, make sure to configure the `mjml.mailjetAPIKey`, `mjml.mailjetAPISecret` and `mjml.mailSender` settings or `mjml.nodemailer` settings in your **user** settings.

Do not save these values into the workspace settings we don't want tokens being commited to Git!

Read more: https://marketplace.visualstudio.com/items?itemName=mjmlio.vscode-mjml

### Validating on multiple clients

You can use a trial for one of these kinds of services: https://www.emailonacid.com/. The goal here is to evaluate that the template looks right in different kinds of e-mail clients and their versions.
