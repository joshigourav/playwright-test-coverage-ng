# Playwright Test Coverage

A [Playwright](https://playwright.dev) extension that collects code coverage from running end-to-end tests. Assumes that code has been  instrumented with [babel-plugin-istanbul](https://github.com/istanbuljs/babel-plugin-istanbul) during the build process.

## Prerequisites

* Playwright test framework
* `babel-plugin-istanbul` plugin
* `nyc` for running tests

```bash
npm i -D @playwright/test babel-plugin-istanbul nyc
```

## Installation

```bash
npm i -D playwright-test-coverage
```

## Usage

Write your Playwright tests as usual, except `require` `test` and `expect` from this package as follows:

```js
// tests/foo.spec.js
const { test, expect } = require("playwright-test-coverage");

// Use test and expect as usual
test('basic test', async ({ page }) => {
  await page.goto('https://playwright.dev/');
  const title = page.locator('.navbar__inner .navbar__title');
  await expect(title).toHaveText('Playwright');
});
```

Then, instrument your front end source code for coverage using the `babel-plugin-istanbul` plugin.

Finally, run your server via `nyc` to capture code coverage. For more details see [istanbul/nyc](https://github.com/istanbuljs/nyc).


## Demo

_Coming soon_

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## Acknowledgements

Inspired by [mxschmitt/playwright-test-coverage](https://github.com/mxschmitt/playwright-test-coverage).

## License
[MIT](https://choosealicense.com/licenses/mit/)