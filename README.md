# ngx-gauge

[![npm version](https://badge.fury.io/js/angularjs-gauge.svg)](https://badge.fury.io/js/angularjs-gauge)
[![Build Status](https://travis-ci.org/ashish-chopra/angular-gauge.png?branch=master)](https://travis-ci.org/ashish-chopra/angular-gauge)
[![peerDependencies Status](https://david-dm.org/ashish-chopra/angular-gauge/peer-status.svg)](https://david-dm.org/ashish-chopra/angular-gauge?type=peer)
[![devDependencies Status](https://david-dm.org/ashish-chopra/angular-gauge/dev-status.svg)](https://david-dm.org/ashish-chopra/angular-gauge?type=dev)
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/dwyl/esta/issues)

A highly customizable Gauge component for **Angular >= 4.3.x** apps and dashboards. It provides many configurationable options to customize according to your needs. Checkout the live demo [here](https://ashish-chopra.github.io/ngx-gauge).

![alt text](https://raw.githubusercontent.com/ashish-chopra/angular-gauge/master/examples/examples.png)


# Getting Started

## step 1: Install `ngx-gauge` Module

```bash
npm install --save ngx-gauge 
```
This will install the current stable version in your `node_modules` directory and save the entry in `package.json`.

## Step 2: Import the **NgxGaugeModule**

```ts
import { NgxGaugeModule } from 'ngx-gauge';

@NgModule({
    ...
    imports: [NgxGaugeModule],
    ...
})
export class AppModule { }

```
Be sure to import `NgxGaugeModule` after Angular's `BrowserModule`, as the import order matters for `NgModules`.]

## Step 3: Use component `<ngx-gauge>` in HTML
By now the module is ready to use in your app. Copy the following code to see a default gauge in action.

```html
<ngx-gauge size="200" type="full" thick="5" min="0" max="120" value="68.2" cap="round" label="Speed"  foreground-color="#ffcc66" background-color="rgba(255,255,255, 0.4)" append="mph"></ngx-gauge>
```

If you face any problem, then raise an issue [here](https://github.com/ashish-chopra/ngx-gauge/issues).

# Configuration Properties

There are plenty of configurable `input` properties available to tune the `Gauge` as per your needs.

| Name      | Description  | Required  | Default value  | Possible values |
| ---       | ---          | ---       | ---               | ---            |
| `size`    | Specifies the size of the canvas in which Gauge will be drawn. It is used as `width` and `height` both. | No       | `200` | Positive Integer           |
| `type`      | Specifies the gauge's type.                     | No        | `"full"`     |  `"full"`, `"semi"`, `"arch"`  |
| `min`  | Specifies the minimum numeric value for gauge's scale.  | No     | `0`  | Any numeric value  |
| `max` | Specified the maximum numeric value for gauge's scale. | No       | `100`  | Any numeric value  |
| `value`          | Specifies the current value of the Gauge in the range specified by `min` and `max`. It is a required attribute.       | Yes       | `undefined`  | Any numeric value |
| `cap`       | The style of line ending at the gauge's end.    | No        | `"butt"`    | `"round"`, `"butt"`           |
| `thick`        | Specified the thickness of the gauge's bar.            | No        | `6`        | Any Positive Integer |
| `label`       | Specifies the text to display below the Gauge's reading.  | No  | `undefined`                | Any String           |
| `foreground-color`         | Specifies the foreground color of the Gauge's scale.                    | No       | `rgba(0, 150, 136, 1)`             |   Any color value string       |
| `background-color`    | Specifies the background color of the Gauge's scale.| No        |    `rgba(0, 0, 0, 0.1)`           |    Any color value string        |
| `append`   | Specifies a `string` appended to the Gauge's reading. For example `"%"` most commonly used. | No        | `undefined`        | Any string           |
| `prepend`      | Specifies a `string` prepended to the Gauge's reading. For example `"$"` in case of financial data displayed in Gauge.                                        | No        | `undefined`            | Any String           |
| `duration`    | Specifies the duration (in milliseconds) of the Gauge's animation | No       | `1500` | Positive Integer           |
| `thresholds` | Specifies an object of threshold values at which the gauge's color changes. Checkout an example [here](#configure-threshold-color-ranges).  | No |  `none` | {}

## Configure Threshold Color Ranges

You can customize the colors of the gauge based on the current value being shown. In order to show different colors when gauge crosses certain value, use property `thresholds`. It takes an object with the threshold value  as `key` and an object with `color` property as `value`. For example: 

```js
....

var thresholdConfig = {
  '0': {color: 'green'},
  '40': {color: 'orange'},
  '75.5': {color: 'red'}
};

....

```

```html
<ng-gauge ...  [thresholds]="thresholdConfig"></ng-gauge>
```
The keys in the threshold object signifies the minimum value at which the color will be applied. For instance, if the gauge's current value is `53.2`, then orange color will be applied because after point `40` every value will be displayed as `orange`, until next threshold is encountered. In this example `75.5` is the next threshold.

# Playground

The examples section is redesigned as a playground where you can play with Gauge by tuning its different parameters. 
And, you can see the result live on-screen. It is good start to get familiar with Gauge.

![alt text](https://raw.githubusercontent.com/ashish-chopra/angular-gauge/master/examples/playground.png)


# Contribution Welcome!

The project is continously evolving with every new release. Give it a star, if you like it. For contribution, setup the development environment as follows:

1. clone and setup the project dependencies

```shell
$> git clone https://github.com/ashish-chopra/ngx-gauge.git
$> npm install
```

2. Use following commands based on what you'd like to do:

```shell
$> npm start             # starts the server at port 3000 and hosts the `/examples` directory.
$> npm test              # runs test suite once and exit.
$> npm run test:watch    # starts the test framework and watch for changes in code.
$> npm run build         # triggers a manual build for library, outputs at `/dist` directory.
```

3. To add a new feature or fix a bug, make sure to create a new branch from `master`.


First thing first, explore the [issue tracker](https://github.com/ashish-chopra/angular-gauge/issues) to find something to contribute. There are tons of other project setup related issues and activities in which you can help. Your feedback could also be a great contribution.

If you face any problem, then raise an issue [here](https://github.com/ashish-chopra/angular-gauge/issues).

# License

[MIT License](https://github.com/ashish-chopra/angular-gauge/blob/master/LICENSE)