# vuejs-donut-simple

> Simple donut chart

![alt text](https://github.com/al3xa96/vuejs-donut-simple/blob/master/src/assets/donut.png)
##Required Properties
````
    percentage: {
      type: Number,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    stroke: {
      type: Number,
      required: true
    }
````
* Percentage: displayed value on chart
* Description: variable's name
* stroke: Chart width

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
