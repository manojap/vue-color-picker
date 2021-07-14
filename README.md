# vue-color-picker

This is a pure CSS color-picker component for Vue/Nuxt project.

[![NPM](https://img.shields.io/npm/v/@codehat/vue-css-loader.svg)](https://www.npmjs.com/package/@codehat/vue-color-picker) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

<img src="./picker.png"/>

## Installation

```bash
npm i --save @codehat/vue-color-picker
```

## Props and other features

**vue-color-picker** come with one prop `selColor` which can be used to set initial color. For dynamically set the color use the `binding` feature.

The component `emit` **colPicked** event which return the selected color. All we have to do is create `method` and receive the `emited` value.


## Usage

```javascript
<template>
   <div class="columns section">
    <div class="column">
      <c-picker :selColor="col"
        @colPicked="changeColor" /> 
      {{ col }}
    </div>
    <div class="column" :style="{ background: col }" >
    <CheckGroup/>
    <p>  
    </p>
    </div>
  </div>
</template>

<script> 
import  VueColorPicker from "@codehat/vue-color-picker" ; 

export default {
  name: "Gallery",
  data() {
    return {
      col: "",
      
    };
  },
  methods: {
    changeColor(value) {
      this.col = value;
    },
    
  },
  components: {
    "c-picker": VueColorPicker,   
      
  },

};
</script>

<style scoped>
.cardContainer {
  position: absolute;
  left: 30px;
  top: 20px;
  text-align: center;
}
.front,
.back {
  position: absolute;
  height: 100%;
  width: 100%;
  background: #ff962d;
  /* line-height: 300px; */
  color: #03446a;
  /* text-align: center; */
  font-size: 18px;
  border-radius: 5px;
  backface-visibility: hidden;
}
.back {
  background: #d90000;
  color: white;
  transform: rotateY(180deg);
}
</style>

```
## License

MIT © [manojap](https://github.com/manojap)