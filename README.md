# stockersa-mern-scss-styled

# 🚀 Javascript full-stack 🚀

## MERN Stack

### React / Express / MongoDB / TypeScript / Material UI / Coingecko API

https://github.com/coding-to-music/stockersa-mern-scss-styled

https://stockersa-mern-scss-styled.herokuapp.com

by Ilias Allek https://github.com/Allek97

https://github.com/Allek97/stockersa

## Summary uses of environment variables:

```java
process.env.NODE_ENV === "development"
process.env.REACT_APP_GOOGLE_MAPS_API_KEY
process.env.REACT_APP_ALPHA_VANTAGE_API_KEY
process.env.REACT_APP_BACKEND_URL
process.env.REACT_APP_TIINGO_API_KEY
```

## Failing to build

```java
> stockersa@0.1.0 build
> react-scripts build

Creating an optimized production build...
Failed to compile.

SyntaxError: unknown: Namespace tags are not supported by default. React's JSX doesn't support namespace tags. You can set `throwIfNamespace: false` to bypass this warning.
   6 |   ...props
   7 | }, svgRef) {
```

## Detailed uses of environment variables:

```java
# mongoose is not used in this project
mongoose_1.default.connect(`${process.env.MONGODB_URI

// Development logging
if (process.env.NODE_ENV === "development") {
    app.use(morgan("dev"));
}

export default function StockMap({ assetAddress, assetName }) {
    const [libraries] = useState(["places"]);

    const { isLoaded, loadError } = useLoadScript({
        googleMapsApiKey: process.env.REACT_APP_GOOGLE_MAPS_API_KEY,
        libraries,
        id: "stockersa",
    });

const axiosInstance = axios.create({
    baseURL: "https://www.alphavantage.co/query",
});

export const getDailyStockForSymbol = (symbol) => {
    return axiosInstance.get("", {
        params: {
            function: "TIME_SERIES_DAIlY",
            symbol,
            apikey: process.env.REACT_APP_ALPHA_VANTAGE_API_KEY,
        },
    });
};


const axiosInstance = axios.create({
    // baseURL: "https://financialmodelingprep.com/api/v3/",
    baseURL: process.env.REACT_APP_BACKEND_URL,
});
const FMPURL = "https://financialmodelingprep.com/api/v3";

export const getDailyAssetPriceFMP = (symbol, startDate, endDate) => {
    return axiosInstance.get(`api/fmp/`, {
        params: {
            url: encodeURI(
                `${FMPURL}/historical-price-full/${symbol}?from=${startDate}&to=${endDate}&apikey=${process.env.REACT_APP_FMP_API_KEY}`
            ),
        },
    });
};

const axiosInstance = axios.create({
    baseURL: process.env.REACT_APP_BACKEND_URL,
});

export const getDailyStockForSymbolTiingo = (
    symbol,
    startDate,
    endDate,
    frequence = "daily"
) => {
    return axiosInstance.get(`api/tiingo/`, {
        params: {
            url: encodeURI(
                `https://api.tiingo.com/tiingo/daily/${symbol}/prices/?startDate=${startDate}&endDate=${endDate}&resampleFreq=${frequence}&format:"json"&token=${process.env.REACT_APP_TIINGO_API_KEY}`
            ),
        },
    });
};


```

## Deploying to Render

This plugin will extract info from Heroku and put it into a Docker file.

```java
heroku plugins:install @renderinc/heroku-import
```

Output:

```java
warning ../../../package.json: No license field
warning ../../../../../../package.json: No license field
warning "eslint-config-oclif > eslint-config-xo-space@0.27.0" has incorrect peer dependency "eslint@>=7.20.0".
warning "eslint-config-oclif > eslint-plugin-mocha@9.0.0" has incorrect peer dependency "eslint@>=7.0.0".
warning "eslint-config-oclif > eslint-plugin-unicorn@36.0.0" has incorrect peer dependency "eslint@>=7.32.0".
warning "eslint-config-oclif > eslint-config-xo-space > eslint-config-xo@0.35.0" has incorrect peer dependency "eslint@>=7.20.0".
warning "eslint-config-oclif > eslint-plugin-unicorn > eslint-template-visitor@2.3.2" has incorrect peer dependency "eslint@>=7.0.0".
warning "eslint-config-oclif > eslint-plugin-unicorn > eslint-template-visitor > @babel/eslint-parser@7.16.3" has incorrect peer dependency "eslint@^7.5.0 || ^8.0.0".
Installing plugin @renderinc/heroku-import... installed v1.1.0
```

```java
heroku render:import --app stockersa-mern-scss-styled
```

Output:

```java

=== Gathering information about Heroku app
Verifying Heroku app exists and CLI is logged in... ✔️
Verifying app is using a single, official Heroku buildpack... ✔️
Getting stack image... heroku-20
Getting and translating plan... Heroku Free $0/mo --> Render Free $0/mo
Getting instance count... 1
Getting custom domains... 0 custom domain(s)
Getting environment variables... 2 environment variable(s)
Getting add-ons... 0 add-on(s)

? Select addons to import.

Create render.yaml file and Dockerfile.render? This will overwrite any existing files with the same name. (y/n): y
Generating render.yaml file... done
Generating Dockerfile.render... done

=== Environment variables excluded from render.yaml
The following environment variables were not included in the generated
  render.yaml file because they potentially contain secrets. You may need to
  manually add them to your service in the Render Dashboard.

- JWT_SECRET:

=== Follow these steps to complete import of service(s) and database(s) to Render
1. Add, commit, and push the generated render.yaml and Dockerfile.render to GitHub or GitLab.
2. Go to https://dashboard.render.com/select-repo?type=iac
3. Search for and select this repository.
4. Verify the plan showing the resources that Render will create, and
   then click 'Create New Resources'.
5. After the resources are deployed, you may need to manually add
   the above environment variables to your Web Service in the Render Dashboard.
   They were not included in the generated render.yaml because they potentially
   contain secrets.
```

<p align="center">
  <a href="https://stockersa.netlify.app/" rel="noopener" target="_blank">
 <img src="https://personal-website-me.s3.amazonaws.com/stockersa-responsive-resized.png" alt="Project thumbnail"></a>
</p>
<h3 align="center">Stockersa</h3>
<div align="center" >
    <a href="https://stockersa.netlify.app" rel="noopener" align="center"> https://stockersa.netlify.app
    
</div>
<br>
<div align="center">

[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE.md)

</div>

---

<p align="center"> Stockersa (3rd project) is a visually animated app that provides financial news, data and commentary, including stock quotes, business news, financial statements,expense reports and key information about companies. It uses financial modeling prep API, it supports over 15000 stocks across multiple exchanges. Whole U.S. market, XETRA, EURONEX, TSX, SEDAR, SEHK and more.
</p>

## 🥳 About This Production <a name = "problem_statement"></a>

After learning how to build RESTful APIs with Explodii, I decided to create something exploiting third party APIs. I went for a stock market APIs. After trying multiple free APIs and trying to combine them to get the maximum of data with a decent request rate. I finally decided to redo everything and go with Financial Modeling Prep API I purchased their starter pack for absolute flexibility.

Charts were used to render the data from the API. I mainly used recharts react library and airbnb visx to build those charts. The features users can use in Stockersa :

- Access real-time stock data, quotes(with price rate of change) and volumes up to 5 years back, with 7 different time periods.
- Get access to the latest news related to the searched stock or the global market in general.
- Get important daily key metrics like P/E Ratio, Earnings Per Share (Eps), market cap, average volume and more.
- Get an overview of the company/corporation of your interests.
- Get access to the yearly financial statements up to 5 years. Includes net income, gross profit, revenue, ebitda and more.
- Get also access to the yearly expense information up to 5 years. With metrics like cost of revenue, research and development expenses, general and administrative expenses, selling and marketing expenses and more.
- Get access to a Google map that tracks the company's headquarter and 65+ global exchanges all over the globe with key information.
  Stockersa is fully responsive, please try it on all devices.

Stockersa is fully responsive, please try it on all devices.

## ⛏️ Built With <a name = "tech_stack"></a>

- [React/Create React App](https://reactjs.org/) - I used Create React App to build user interfaces in this web application.
- [SCSS/Styled-Components](https://styled-components.com/) - I used SCSS with Block Element Modifier (BEM) notation and Styled-Components to design this web app.
- [Node.js/ Express.js](https://expressjs.com/) - I used Node.js/ Express.js to build a server that will consume the third party APIs calls.
- [Netlify](https://www.netlify.com/) - I deployed the react app on the Netlify cloud.
- [Heroku](https://www.heroku.com/) - I deployed the server on heroku.

## 🧐 For more details <a name = "tech_stack"></a>

Please visit : https://iliasallek.com/stockersa/

## GitHub

```java
git init
git add .
git remote remove origin
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:coding-to-music/stockersa-mern-scss-styled.git
git push -u origin main
```

## Heroku

```java
heroku create stockersa-mern-scss-styled
```

## Heroku MongoDB Environment Variables

```java
heroku config:set

heroku config:set JWT_SECRET="secret"

heroku config:set PUBLIC_URL="https://stockersa-mern-scss-styled.herokuapp.com"
```

## Push to Heroku

```java
git push heroku

# or

npm run deploy
```

## update npm packages

```java
npm install -g npm-check-updates
```

Output:

```java

```

```java
ncu -u
```

Output:

```java
Upgrading /mnt/volume_nyc1_01/stockersa-mern-scss-styled/package.json
[====================] 7/7 100%

 cookie-parser   ^1.4.5  →   ^1.4.6
 express        ^4.17.1  →  ^4.17.3
 helmet          ^4.6.0  →   ^5.0.2

removed 3 packages, changed 263 packages, and audited 264 packages in 10s

29 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```

```java
npm install
```

Output:

```java
changed 1 package, and audited 106 packages in 954ms

3 packages are looking for funding
  run `npm fund` for details
```

## Client directory

```java
cd client

ncu -u
```

```java
Upgrading /mnt/volume_nyc1_01/stockersa-mern-scss-styled/client/package.json
[====================] 63/63 100%

 @pmndrs/branding                     0.0.7  →          0.0.8
 @reach/combobox                    ^0.15.0  →        ^0.16.5
 @react-google-maps/api              ^2.1.1  →         ^2.8.1
 @react-three/drei                   ^4.1.8  →         ^9.5.0
 @react-three/fiber                 ^6.0.16  →        ^8.0.12
 @testing-library/jest-dom         ^5.11.10  →        ^5.16.4
 @testing-library/react             ^11.2.6  →        ^13.1.1
 @testing-library/user-event        ^12.8.3  →        ^14.1.1
 @visx/group                         ^1.7.0  →         ^2.1.0
 @visx/shape                        ^1.12.0  →         ^2.4.0
 @visx/text                         ^1.10.0  →         ^2.3.0
 axios                              ^0.21.1  →        ^0.26.1
 d3                                  ^4.0.0  →         ^7.4.4
 date-fns                           ^2.22.1  →        ^2.28.0
 dotenv                              ^8.2.0  →        ^16.0.0
 fusioncharts                       ^3.17.0  →        ^3.18.0
 http-proxy-middleware               ^2.0.1  →         ^2.0.5
 moment                             ^2.29.1  →        ^2.29.3
 prop-types                         ^15.7.2  →        ^15.8.1
 react                              ^17.0.2  →        ^18.0.0
 react-cool-onclickoutside           ^1.6.2  →         ^1.7.0
 react-dom                          ^17.0.2  →        ^18.0.0
 react-icons                         ^4.2.0  →         ^4.3.1
 react-intersection-observer        ^8.32.0  →        ^8.34.0
 react-query                        ^3.16.1  →        ^3.35.0
 react-responsive             ^9.0.0-beta.3  →  ^9.0.0-beta.6
 react-router-dom                    ^5.2.0  →         ^6.3.0
 react-scripts                        4.0.3  →          5.0.1
 react-scroll                        ^1.8.3  →         ^1.8.7
 recharts                            ^2.0.9  →         ^2.1.9
 sass                               ^1.41.0  →        ^1.50.1
 sass-loader                        ^12.1.0  →        ^12.6.0
 stripe                            ^8.150.0  →       ^8.218.0
 styled-components                   ^5.2.3  →         ^5.3.5
 three                             ^0.124.0  →       ^0.139.2
 three-globe                        ^2.18.6  →        ^2.24.4
 use-places-autocomplete             ^1.9.1  →         ^2.0.0
 web-vitals                          ^1.1.1  →         ^2.1.4
 eslint-config-prettier              ^8.1.0  →         ^8.5.0
 eslint-plugin-html                  ^6.1.2  →         ^6.2.0
 eslint-plugin-prettier              ^3.3.1  →         ^4.0.0
 mongoose                           ^5.12.7  →         ^6.3.0
 prettier                            ^2.2.1  →         ^2.6.2

Run npm install to install new versions.
```
