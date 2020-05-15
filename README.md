## Yew PWA Minimal

This project contains a minimal [Progressive Web App (PWA)](https://en.wikipedia.org/wiki/Progressive_web_application) using [`Yew`](https://github.com/yewstack/yew). It is based on the [`yew-wasm-pack-minimal`](https://github.com/yewstack/yew-wasm-pack-minimal) example and James Johnson's [Simple PWA Tutorial](https://medium.com/james-johnson/a-simple-progressive-web-app-tutorial-f9708e5f2605). 

Compared to [`yew-wasm-pack-minimal`](https://github.com/yewstack/yew-wasm-pack-minimal), the following changes were implemented:
- Add a manifest file (`manifest.json`) describing the PWA.
- Add a service worker (`sw.js`) that allows the app to work offline.
- Add an icon (`icon-256.png`).
- Register the service worker and manifest file in `index.html`.

## Build

Follow the instructions at https://github.com/yewstack/yew-wasm-pack-minimal to build and bundle the project. Basically:
```
wasm-pack build --target web
rollup ./main.js --format iife --file ./pkg/bundle.js
```

## Test / Deploy

PWAs need to be accessed via https. If you don't have a https server set up already, the simplest way to test your PWA is to use Github Pages. Create a new project, activate Github Pages for the master branch and upload the following files to it:

```
pkg/bundle.js
pkg/yew_wasm_pack_minimal_bg.wasm
icon-256.png
index.html
manifest.json
sw.js
```

The website should become available under https://USERNAME.github.io/PROJECT_NAME after a couple of minutes. I've uploaded the deployment files to https://github.com/fkohlgrueber/yew-pwa-deploy. The PWA is available under https://fkohlgrueber.github.io/yew-pwa-deploy/.

Feel free to open issues if things don't work for you.
