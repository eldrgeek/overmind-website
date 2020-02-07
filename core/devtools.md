# Devtools

## VS Code

For the best experience you should install the [OVERMIND DEVTOOLS](https://marketplace.visualstudio.com/items?itemName=christianalfoni.overmind-devtools-vscode) extension. This will allow you to work on your application without leaving the IDE at all.

![](../.gitbook/assets/amazing_devtools.png)

{% hint style="info" %}
If you are using the **Insiders** version of VSCode the extension will not work. It seems to be some extra security setting.
{% endhint %}

## Standalone app

Alternatively you can install the standalone application of the devtools. You can start it with the NPM executor as:

```javascript
npx overmind-devtools
```

You can also install the devtools with your project, allowing you to lock a specific version of the devtools to your project:

```javascript
npm install overmind-devtools
```

If you are planning on running overmind-devtools from the command line (for example with CodeSandbox) you'll want to install it this way:

```javascript
npm install -g overmind-devtools
```

With the package [CONCURRENTLY](https://www.npmjs.com/package/concurrently) you can start the devtools as you start your build process:

```text
npm install overmind-devtools concurrently
```

{% code title="package.json" %}
```javascript
{
  ...
  "scripts": {
    "start": "concurrently \"overmind-devtools\" \"someBuildTool\""
  },
  ...
}
```
{% endcode %}

### Running on Chromebook
To run overmind-devtools using the Crouton Linux distribution that's provided for Chromebooks you'll need to configure it this way:

```javascript
app = createOvermind(config, {
    devtools: 'penguin.termina.linux.test:XXXX'
  });
```

where `XXXX` is the port you'll be using.

## Hot Module Replacement

A popular concept introduced by Webpack is [HMR](https://webpack.js.org/concepts/hot-module-replacement/). It allows you to make changes to your code without having to refresh. Overmind automatically supports HMR. That means when **HMR** is activated Overmind will make sure it updates and manages its state, actions and effects. Even the devtools will be updated as you make changes.

