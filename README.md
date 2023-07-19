# Star pairs
[![Join the chat at https://gitter.im/firpov/star-pairs3](https://badges.gitter.im/firpov/star-pairs3.svg)](https://gitter.im/firpov/star-pairs3?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

A static single web page application to project pairs of stars in real time and
display information when mousing over them.

[![Star pairs screenshot](https://github.com/firpov/star-pairs3/raw/master/screenshot.png??raw=true)](https://firpov.github.io/star-pairs3/)


This tool is used every evening at the [Gemini Observatory] to find a pair of
suitable stars to perform the fine tuning and shaping of the primary and
secondary mirrors.

The list of pairs of stars is stored on `pairs.json` in equatorial coordinates.
When displayed the coordinates are transformed in real time (every second) to
altazimuth (local) coordinates and projected at the latitude and longitude of
[Cerro Pachón].

When mousing over a pair the following info is displayed:

  - **Identification number**
  - **V Magnitude**: Bigger circles represent brighter stars. The range of the
    magnitudes goes approximately from 3 to 8 magnitudes.

## For Gemini operators only

At the [Gemini Observatory] the operator decides which pair is suitable for the
night depending on the conditions. The tuning is normally done between 65 and 80
degrees of elevation in order to be optimal for the night. In case the pairs are
used to monitor the counts under cloudy conditions, or other engineering
procedure, the pair is chosen depending on the desired situation. Once the pair
is selected the operator has to select the desired pair in the TCC configuration
manager, and set the fields with the desired configuration. Once this is done
the telescope can be slewed.

## Installation

There is a live version at https://firpov.github.io/star-pairs3/ but it
can be run locally.

1. Install a JavaScript package manager like [`yarn`] or [`npm`]. Your method of
   installation would depend on your preferences and platform. For example:

   - MacOS:
   ```sh
   $ brew install yarn
   ```

   - Fedora
   ```
   $ sudo dnf install yarn
   ```

   - Windows:
   ```sh
   $ choco install yarn
   ```

   You can check more methods of installation at [Yarn install
   documentation](https://yarnpkg.com/lang/en/docs/install/).

1. Clone

   ```sh
   $ git clone https://github.com/firpov/star-pairs3.git
   ```

1. Run

   ```sh
   $ yarn start
   ```

   Open your browser and point it to http://localhost:3000.

1. Deploy

   ```sh
   $ yarn build
   ```

   and copy the files in `build/static` to wherever you want to host it from.

   You can also use [other
   methods](https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#deployment)
   of deployment provided by [`create-react-app`].

# References

* LST and equatorial to local coordinates calculations:
  http://www.stargazing.net/kepler/altaz.html

* [`d3`] example with custom sky projection: https://bl.ocks.org/mbostock/7784f4b2c7838b893e9b

* [`d3-celestial`]: Web based celestial map.

# Contact

You may reach us on Gitter

[![Join the chat at https://gitter.im/firpov/star-pairs3](https://badges.gitter.im/firpov/star-pairs3.svg)](https://gitter.im/firpov/star-pairs3?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

or writing an email to:

* Manuel Gomez-Jimenez, *Science Operations Specialist* at [Gemini Observatory]: <mgomez@gemini.edu>
* Danny Navarro, *Software Engineer* at [Gemini Observatory]: <dnavarro@gemini.edu>

[Gemini Observatory]: https://www.gemini.edu/
[Cerro Pachón]: https://en.wikipedia.org/wiki/Cerro_Pachón
[`yarn`]: https://yarnpkg.com/
[`npm`]: https://www.npmjs.com/
[`d3`]: https://d3js.org/
[`create-react-app`]: https://github.com/facebook/create-react-app
[`d3-celestial`]: https://github.com/ofrohn/d3-celestial
