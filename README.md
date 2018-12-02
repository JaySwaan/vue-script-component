# Vue Script Component
A component to enable scripts to be loaded within the template tags of a .vue file.

Since I couldn't find a generic VueJS component to load ads, I made my own. While this component was initially built to load third-party ads, it should be able to load any javascript your pretty little hearts desire.

## Table of Contents
- [Installation](#installation)
- [Basic Usage](#basic-usage)
- [Conditional Usage](#conditional-usage)
- [Demo](#demo)
- [Dependencies](#dependencies)

## Installation

``` bash
npm install vue-script-component
```

## Basic Usage

Find a *.vue file that you want to load a script in, and...
``` vue
<template>
    <div>
        <VueScriptComponent script='<script type="text/javascript"> alert("Peekaboo!"); </script>'/>
    <div>
</template>

<script>
import VueScriptComponent from 'vue-script-component'

export default {
  ...
  components: {
    ...
    VueScriptComponent
  }
  ...
}
</script>

```

## Conditional Usage

Need to execute a script on the fly? VSC can do that...
``` vue
<template>
    <div>
        <VueScriptComponent v-if="someVar" script='<script type="text/javascript"> alert("Peekaboo!"); </script>'/>
        <button @click.prevent="someVar = !someVar">Peekaboo</button>
    <div>
</template>

<script>
import VueScriptComponent from 'vue-script-component'

export default {
  data() {
    return {
        someVar: false
    }
  },
  components: {
    ...
    VueScriptComponent
  }
  ...
}
</script>

```

## Demo

You can find this approach being used in one of my websites https://imgsurv.com . It's a temporary image hosting site to help share images between people no matter the platform. The ads shown on the site are from Propeller at the time of writing.

## Dependencies

This package has 2 dependencies that are required in order for it ro run. Both are available through NPM, find the links below.
1. [postscribe](https://www.npmjs.com/package/postscribe)
2. [document-ready](https://www.npmjs.com/package/document-ready)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
