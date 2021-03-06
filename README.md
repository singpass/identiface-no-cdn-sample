# CDN-free SingPass Face Example for HTML5

![NDI-api Logo](https://www.ndi-api.gov.sg/assets/img/ndi-api-logo.png)

## Instructions

> Note: Current version of iProov is 3.1.3 as at 15 January 2021. If the version has changed, simply run `npm upgrade` on the root folder.

1. Download this repo
2. On macOS, install npm first if it's not installed.
3. Then, run `run.sh` in Terminal. It will run a `http-server` package using `npx`.

## Source Code

### dist folder 

**/dist** contains the build files for a static Vue.js SPA using the Nuxt framework. It also contains the offline build for iProov dependencies. 

The nuxt dependencies of ```code-prettify``` and ```materialdesignicons.min.css``` had been updated to read from local directory instead of cdn.

To download the code-prettify, refer to [code-prettify npm package](https://www.jsdelivr.com/package/npm/code-prettify) for all the files. You should be able to download the package from there. Here are the next steps on what you need to do:

1. Unzip the package
2. Copy the **code-prettify** folder into **/dist**

To download the materialdesignicons.min.css, refer to [materialdesignicons cdn](http://cdn.materialdesignicons.com/5.0.45/css/materialdesignicons.min.css). Create a ```blank materialdesignicons.min.css``` file and copy the content into it. 

## How it works

We have a QuickStart backend portal where your frontend (this POC) code can call to retrieve the iProov token and validate results.

The assets source at https://cdn.iproov.app/ – where the typography, verification engine, and other files are stored in a CDN.

To download the assets files, refer to [iProov's npm package](https://www.jsdelivr.com/package/npm/@iproov/web) for all the files. You should be able to download the package from there. Here are the next steps on what you need to do:

1. Unzip the package
2. Copy the **iproov-assets** folder into **/dist**
3. Copy the **spface.js** file from your asset folder into the **/dist** 

Since this simple POC is using `http-server` to serve the static content, it serves through port `8080`. We've hard-coded `assets_url` to point to `assets_url="/"`.

You could take a look at this implementation in the **/pages** folder.


## Development

To tinker or run the dev server, simply run the following in `Terminal`:

1. `npm install`
2. `npm run dev`

## Test Environment

To run using `http-server` and test whether your page is working, simply run the folloing in `Terminal`:

1. `npm install`
2. `npm run generate` - this will generate the dist folder
3. `sh run.sh` 

When you try scanning the face, you will probably encounter cors error. To fix that you need to deploy the `dist` folder on a static hosted page (e.g. AWS S3 bucket)

## Support/Queries

Please contact biometrics_support@ndi.gov.sg if you have any queries.

## Acknowledgements

[iProov Web SDK Documentation](https://github.com/iProov/web)
