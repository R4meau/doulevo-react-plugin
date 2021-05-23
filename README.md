# doulevo-react-plugin

A Reactjs plugin for [Doulevo](https://github.com/doulevo/doulevo). It uses Create React App (CRA).

For Nextjs, there will be a different plugin available soon.
## Usage

This documentation assumes you [already installed Doulevo on your system](https://github.com/doulevo/doulevo/#readme).

### Creating a new React project

Use the following command to create a new React project using this plugin, directly from GitHub:
```
doulevo create <my-project> --force --plugin-url=https://github.com/r4meau/doulevo-react-plugin.git --debug
```

Replace `<my-project>` with your project/directory name.

Answer the questionnaire based on your preferences.

Then cd into your new directory. You will notice your new React project and your `doulevo.json` configuration file:
```
cd <my-project>
ls -la
```

### Running in development

In development mode, your React app will still autoreload on file change. Simply run the following command within your directory to get it running:

```
doulevo up --plugin-url=https://github.com/r4meau/doulevo-react-plugin.git --debug
```

## Deploying

In production mode, your React app is built into static files and is served through a Caddy server instance with SSL/TLS encryption. When creating your project, you were given the option (through the plugin questionnaire) to provide a domain name.

If you chose to skip it, you should have a file in your `./caddy/` directory called `Caddyfile` which contains instructions for the Caddy server to serve your React app. It should look like:

```
localhost {
  log {
    output file /var/log/caddy/access.log
  }

  encode gzip
  root * /srv
  try_files {path} /index.html
  file_server
}
```

All you have to do before deploying is to update the domain name to yours. i.e.:

```
mywebsite.com {
  log {
    output file /var/log/caddy/access.log
  }

  encode gzip
  root * /srv
  try_files {path} /index.html
  file_server
}
```

TODO: Add Doulevo deployment command here

## About the templates

This plugin comes with two templates:

- react-ts
- react-js

The templates are based off of the default CRA JS/TS generated starter files. Refer to the `react-scripts` dependency version in `package.json` to know which version of CRA was used last.


### For contributors to this plugin

To update CRA, [follow this guide](https://create-react-app.dev/docs/updating-to-new-releases).

To update React, [follow this one](https://stackoverflow.com/a/49829751/927559). Then send us a pull request.

You have to do this for both the `-ts` and the `-js` versions.

## Functionalities

- [ ] Asks user to pick whether they want to use JS or TS
- [ ] Asks user for the initial version number of their project (for their `package.json`)
- [ ] Provides a base documentation in the README.md file
- [ ] Asks user whether they want to use yarn or npm
- [ ] Production: asks user for a domain name to generate the right Caddyfile for serving the static files with SSL encryotion
