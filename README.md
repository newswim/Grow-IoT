# Grow-IoT

[![Backers on Open Collective](https://opencollective.com/Grow-IoT/backers/badge.svg)](#backers) [![Sponsors on Open Collective](https://opencollective.com/Grow-IoT/sponsors/badge.svg)](#sponsors) [![Gitter](https://img.shields.io/gitter/room/nwjs/nw.js.svg)](https://gitter.im/CommonGarden/Grow-IoT) [![BSD license](https://img.shields.io/badge/license-BSD--2--Clause-blue.svg)](https://github.com/CommonGarden/Grow-IoT/blob/master/LICENSE) [![Build Status](https://travis-ci.org/CommonGarden/Grow-IoT.svg?branch=master)](https://travis-ci.org/CommonGarden/Grow-IoT)

The Grow-IoT project is managed as a mono-repo with a bunch of seperately published packages such as:
* [Grow.js](https://github.com/CommonGarden/Grow-IoT/tree/development/packages/Grow.js)
* [Thing.js](https://github.com/CommonGarden/Grow-IoT/tree/development/packages/Thing.js)
* [grow-graphql-api-server](https://github.com/CommonGarden/Grow-IoT/tree/development/packages/graphql-api)
* [rest-api](https://github.com/CommonGarden/Grow-IoT/tree/development/packages/rest-api)

See our [basic Raspberry pi example](https://github.com/CommonGarden/BasicRaspberryPiExample) to get started with devices.

## Installing Grow-IoT

You need to install [Meteor](https://www.meteor.com/) first (if you haven't already). 

You will also need to install [Lerna](https://github.com/lerna/lerna), which we use to manage all the packages that comprise Grow-IoT!

```bash
npm install -g lerna
```

Then clone the repo and enter the new directory:

```bash
git clone https://github.com/CommonGarden/Grow-IoT
cd Grow-IoT
```

Finally install the needed software dependencies:

```
meteor npm install
lerna bootstrap
```

Start the Grow-IoT server with the `meteor` command:

```
meteor
```

And that's it! Visit http://localhost:3000 with your browser of choice; you should now have the application running.

## Connecting devices (or virtual things)
Create a new device (click the '+' button) and create a device `uuid` and `token`. Then run (in a seperate terminal):

```bash
node tests/test-grow-hub.js
```
Paste in the `uuid` and `token` you created and presto! You've connected your first thing to Grow-IoT.

You can find then component for this device in `imports/things/GrowHub.jsx`.

# Connecting sensors and actuators

In the `packages` directory, we've started 2 libraries to help you connect sensors and actuators and create grow systems out of them.
* [Thing.js](https://github.com/CommonGarden/Grow-IoT/tree/development/packages/Thing.js): A general purpose internet of things library... basically a fancy event emitter
* [Grow.js](https://github.com/CommonGarden/Grow-IoT/tree/development/packages/Grow.js): extends the Thing class with a bunch of useful things for growers like scheduling, registering listeners and alerts, etc.

Hardware examples live in the `.examples` folder (the folder is hidden, because Meteor is dumb and tries to build everything). The corresponding UI components live in`imports/things/`.

**See [Thing.js](https://github.com/CommonGarden/Grow-IoT/tree/development/packages/Thing.js) for more info on creating and connecting devices.**

### Adding custom components
To do so:

1. Make a new `CustomComponent.jsx` file in `imports/things/'` or `yarn add package-name`
2. Open `imports/things/index.js`.
3. `import CustomComponent from './CustomComponent'`
4. Lastly, add `CustomComponent` to the exported `components` object.

Example grow systems:
* https://github.com/CommonGarden/Fermenter
* https://github.com/CommonGarden/CompostBrewer

More on the way! Contributions welcome!

# Organization
In the repo you'll find the following directories and files:

File/Folder   | Provides
--------------|----------------------------------------------------------------
`.meteor`     | Meteor stuff, well documented in [other places](http://docs.meteor.com/#/full/).
`.sandstorm`  | Sandstorm.io stuff
`client`      | Imports things and starts the React app.
`imports`     | API, UI, and thing examples live here
`packages`    | Grow.js and Thing.js live here.
`public`      | Fonts and other static, public assets live here.
`tests`       | Unit and Thread conformance tests
`server`      | Imports the server code.
`tests`       | Hmmm....

Our [wiki](https://github.com/CommonGarden/Grow-IoT/wiki) also contains a growing assortment of useful info, including:
* [Cloud setup](https://github.com/CommonGarden/Grow-IoT/wiki/Cloud-setup)
* [Elastic support](https://github.com/CommonGarden/Grow-IoT/wiki/Elastic)
* [Influx support](https://github.com/CommonGarden/Grow-IoT/wiki/Influx-DB)
* [Graphana setup](https://github.com/CommonGarden/Grow-IoT/wiki/Grafana-Setup)
* [Running locally](https://github.com/CommonGarden/Grow-IoT/wiki/Running-locally)
* [Supported hardware](https://github.com/CommonGarden/Grow-IoT/wiki/Supported-hardware)

## Roadmap

There's a lot to do.
* [CoAP](https://github.com/CommonGarden/Grow-IoT/issues/300) (it's been started but not tested very well)
* [Graph-QL](https://github.com/CommonGarden/Grow-IoT/issues/315)
* [User profiles](https://github.com/CommonGarden/Grow-IoT/issues/382)
* Better data visualizations (timeseries without having to use grafana anyone?)
* [Options to replace mongodb and influxdb](https://github.com/CommonGarden/Grow-IoT/issues/417).
* [Logic ui](https://github.com/CommonGarden/Grow-IoT/issues/306) (a.k.a. advanced interoperablity) a.k.a. "Swarms"
* [Environments](https://github.com/CommonGarden/Grow-IoT/issues/311) (creating groups of things)
* [Administration and device management](https://github.com/CommonGarden/Grow-IoT/issues/370) (a green house or lab involves more than one user often)


## Contributors

This project exists thanks to all the people who contribute. [[Contribute]](CONTRIBUTING.md).
<a href="graphs/contributors"><img src="https://opencollective.com/Grow-IoT/contributors.svg?width=890" /></a>


## License
Grow-IoT is released under the 2-Clause BSD License, sometimes referred to as the "Simplified BSD License" or the "FreeBSD License".
