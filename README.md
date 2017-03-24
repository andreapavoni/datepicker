# Vue Bulma Datepicker (Alternative)

A fork of [Vue Bulma Datepicker](https://github.com/vue-bulma/datepicker) based on [flatpickr](https://github.com/chmln/flatpickr). It follows Bulma versions and fixes some minor bugs from the original version. I had to fork the original project because I needed a quick fix.

## Installation

**Update: 2017-03-24: it's not yet published on NPM repository, so for the moment, just add the github repo as source.** 

```
$ npm install vue-bulma-datepicker-alt --save
```

## Examples

### Single Input

```vue
<template>
  <datepicker placeholder="European Format ('d-m-Y')" :config="{ dateFormat: 'd-m-Y', static: true }"></datepicker>
</template>

<script>
import Datepicker from 'vue-bulma-datepicker'

export default {
  components: {
    Datepicker
  }
}
</script>
```

### Wrap Input

```vue
<template>
  <datepicker :config="{ wrap: true }" readonly>
    <a class="button" data-toggle><i class="fa fa-calendar"></i></a>
    <a class="button" data-clear><i class="fa fa-close"></i></a>
  </datepicker>
</template>

<script>
import Datepicker from 'vue-bulma-datepicker'

export default {
  components: {
    Datepicker
  }
}
</script>
```

## Badges

![](https://img.shields.io/badge/license-MIT-blue.svg)
![](https://img.shields.io/badge/status-stable-green.svg)
