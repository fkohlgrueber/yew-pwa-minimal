## Yew PWA Minimal

This project contains a minimal [Progressive Web App (PWA)](https://en.wikipedia.org/wiki/Progressive_web_application) using [`Yew`](https://github.com/yewstack/yew). It is based on [Yew's sample app](https://yew.rs/docs/getting-started/build-a-sample-app) and James Johnson's [Simple PWA Tutorial](https://medium.com/james-johnson/a-simple-progressive-web-app-tutorial-f9708e5f2605). 

Compared to [Yew's sample app](https://yew.rs/docs/getting-started/build-a-sample-app), the following changes were implemented:
- Add a manifest file (`manifest.json`) describing the PWA.
- Add a service worker (`service_worker.js`) that allows the app to work offline.
- Add an icon (`icon-256.png`).
- Register the service worker and manifest file in `index.html`.
- Add a trunk config (`Trunk.toml`) that sets the public url to `./`. The default is root (`/`), which doesn't work if the project files aren't served at the domain's root. The change allows to deploy the files to github pages (https://USERNAME.github.io/PROJECT_NAME).

## Preparation

Install the `wasm32-unknown-unknown` target:

```
rustup target add wasm32-unknown-unknown
```

Install [`trunk`](https://trunkrs.dev/):

```
cargo install trunk
```

## Build

Build using `trunk`:

```
trunk build
# or
trunk build --release
```

## Test / Deploy

PWAs need to be accessed via https. If you don't have a https server set up already, the simplest way to test your PWA is to use Github Pages. Create a new project, activate Github Pages for the master branch and upload the contents of the `dist/` folder to it.

The website should become available under https://USERNAME.github.io/PROJECT_NAME after a couple of minutes. I've uploaded the deployment files to https://github.com/fkohlgrueber/yew-pwa-deploy. The PWA is available under https://fkohlgrueber.github.io/yew-pwa-deploy/.

Feel free to open issues if anything doesn't work for you.
