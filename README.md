# npmtest-electron-react-boilerplate

#### basic test coverage for  [electron-react-boilerplate (v0.10.0)](https://github.com/chentsulin/electron-react-boilerplate#readme)  [![npm package](https://img.shields.io/npm/v/npmtest-electron-react-boilerplate.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-electron-react-boilerplate) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-electron-react-boilerplate.svg)](https://travis-ci.org/npmtest/node-npmtest-electron-react-boilerplate)

#### Electron application boilerplate based on React, React Router, Webpack, React Hot Loader for rapid application development

[![NPM](https://nodei.co/npm/electron-react-boilerplate.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/electron-react-boilerplate)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-electron-react-boilerplate/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-electron-react-boilerplate/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-electron-react-boilerplate/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/test-report.html](https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-electron-react-boilerplate/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-electron-react-boilerplate/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-electron-react-boilerplate/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-electron-react-boilerplate/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-electron-react-boilerplate/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "electron-react-boilerplate",
    "productName": "ElectronReact",
    "version": "0.10.0",
    "description": "Electron application boilerplate based on React, React Router, Webpack, React Hot Loader for rapid application development",
    "main": "main.js",
    "scripts": {
        "test": "cross-env NODE_ENV=test mocha --compilers js:babel-register --recursive --require ./test/setup.js test/**/*.spec.js",
        "test-watch": "npm test -- --watch",
        "test-e2e": "cross-env NODE_ENV=test mocha --compilers js:babel-register --require ./test/setup.js --require co-mocha ./test/e2e.js",
        "lint": "eslint app test *.js",
        "hot-server": "node -r babel-register server.js",
        "build-main": "cross-env NODE_ENV=production node -r babel-register ./node_modules/.bin/webpack --config webpack.config.electron.js --progress --profile --colors",
        "build-renderer": "cross-env NODE_ENV=production node -r babel-register ./node_modules/.bin/webpack --config webpack.config.production.js --progress --profile --colors",
        "build": "npm run build-main && npm run build-renderer",
        "start": "cross-env NODE_ENV=production electron ./",
        "start-hot": "cross-env HOT=1 NODE_ENV=development electron -r babel-register ./main.development",
        "package": "cross-env NODE_ENV=production node -r babel-register package.js",
        "package-all": "npm run package -- --all",
        "postinstall": "node node_modules/fbjs-scripts/node/check-dev-engines.js package.json",
        "dev": "concurrently --kill-others \"npm run hot-server\" \"npm run start-hot\""
    },
    "bin": {
        "electron": "./node_modules/.bin/electron"
    },
    "repository": {
        "type": "git",
        "url": "git+https://github.com/chentsulin/electron-react-boilerplate.git"
    },
    "author": {
        "name": "C. T. Lin",
        "url": "https://github.com/chentsulin"
    },
    "license": "MIT",
    "bugs": {
        "url": "https://github.com/chentsulin/electron-react-boilerplate/issues"
    },
    "keywords": [
        "electron",
        "boilerplate",
        "react",
        "react-router",
        "flux",
        "webpack",
        "react-hot"
    ],
    "homepage": "https://github.com/chentsulin/electron-react-boilerplate#readme",
    "devDependencies": {
        "asar": "^0.11.0",
        "babel-core": "^6.7.6",
        "babel-eslint": "^6.0.2",
        "babel-loader": "^6.2.4",
        "babel-plugin-add-module-exports": "^0.1.2",
        "babel-plugin-webpack-loaders": "^0.4.0",
        "babel-polyfill": "^6.7.4",
        "babel-preset-es2015": "^6.6.0",
        "babel-preset-react": "^6.5.0",
        "babel-preset-react-hmre": "^1.1.1",
        "babel-preset-stage-0": "^6.5.0",
        "babel-register": "^6.7.2",
        "chai": "^3.5.0",
        "chromedriver": "^2.21.2",
        "co-mocha": "^1.1.2",
        "concurrently": "^2.0.0",
        "cross-env": "^1.0.7",
        "css-loader": "^0.23.1",
        "del": "^2.2.0",
        "electron-packager": "^6.0.2",
        "electron-prebuilt": "^0.37.6",
        "electron-rebuild": "^1.1.3",
        "eslint": "^2.8.0",
        "eslint-config-airbnb": "^7.0.0",
        "eslint-plugin-jsx-a11y": "^0.6.2",
        "eslint-plugin-react": "^4.3.0",
        "express": "^4.13.4",
        "extract-text-webpack-plugin": "^1.0.1",
        "fbjs-scripts": "^0.6.0",
        "jsdom": "^8.4.0",
        "json-loader": "^0.5.4",
        "minimist": "^1.2.0",
        "mocha": "^2.4.5",
        "node-libs-browser": "^1.0.0",
        "react-addons-test-utils": "^15.0.1",
        "redux-devtools": "^3.2.0",
        "redux-devtools-dock-monitor": "^1.1.1",
        "redux-devtools-log-monitor": "^1.0.11",
        "redux-logger": "^2.6.1",
        "selenium-webdriver": "^2.53.1",
        "sinon": "^1.17.3",
        "style-loader": "^0.13.1",
        "webpack": "^1.13.0",
        "webpack-dev-middleware": "^1.6.1",
        "webpack-hot-middleware": "^2.10.0"
    },
    "dependencies": {
        "css-modules-require-hook": "^4.0.0",
        "electron-debug": "^0.6.0",
        "font-awesome": "^4.6.1",
        "postcss": "^5.0.19",
        "react": "^15.0.1",
        "react-dom": "^15.0.1",
        "react-redux": "^4.4.5",
        "react-router": "^2.2.4",
        "react-router-redux": "^4.0.2",
        "redux": "^3.4.0",
        "redux-thunk": "^2.0.1",
        "source-map-support": "^0.4.0"
    },
    "devEngines": {
        "node": "4.x || 5.x",
        "npm": "2.x || 3.x"
    }
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
