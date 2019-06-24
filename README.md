# nc-form

nc-form widget for [ncform](https://github.com/ncform/ncform)

## Install and basic usage

```
npm i -s @ncform/nc-form
```

**Add the widget**

```
import ncForm from '@ncform/nc-form';

Vue.use(vueNcform, { extComponents: {ncForm} });

// or vm.$ncformAddWidget({name: 'ncForm', widget: ncForm});

```

**Use the widget**

```
{
  "type": "object",
  "properties": {
    "name": {
      "type": "object",
      "widget": "nc-form",
      "widgetConfig": {
        "schema": {
          "type": "object",
          "properties": {
            "name": {
              "type": "string"
            }
          }
        }
      }
    }
  }
}
```

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

You only need to care about `src/components/index.vue`

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Run your end-to-end tests
```
npm run test:e2e
```

### Run your unit tests
```
npm run test:unit
```
