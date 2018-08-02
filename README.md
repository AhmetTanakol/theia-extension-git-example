# Hello World Extension Example
The example of how to build the Theia-based applications with custom extensions by installing from github repos
The browser application can consume multiple custom extension. In this example, we have 2 different menu commands
"Hello World" and "Goodbye World". `goodbye-world-extension` is installed from a public github repo and added as a dependency
in our browser application. If you would like to consume a custom extension as a part of another extension,
you need to update `package.json` of your extension which will consume the custom extension that you want.


## Getting started

Install [nvm](https://github.com/creationix/nvm#install-script).

    curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.5/install.sh | bash

Install npm and node.

    nvm install 8
    nvm use 8

Install yarn.

    npm install -g yarn

## Running the browser example

    yarn install
    cd browser-app
    // this line adds our custom extension as a dependency in the browser-app workspace
    yarn workspace browser-app add git+ssh://git@github.com:AhmetTanakol/goodbye-world.git#v0.6.0
    cd ..
    yarn prepare
    cd browser-app
    yarn start

Open http://localhost:3000 in the browser.
