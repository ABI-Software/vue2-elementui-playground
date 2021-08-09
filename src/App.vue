<template>
  <div id="app">
        <test-radio
          v-for="item in labels"
          v-bind:key="item.label"
          v-model="radioVal"
          :label="item.label"
          :display="item.display"
        />
  </div>
</template>

<script>
/* eslint-disable no-alert, no-console */
// optionally import default styles
import TestRadio from './components/radio'

export default {
  name: 'app',
  components: {
    TestRadio
  },
  data: function() {
    return {
      labels: [
        {
          label: 1,
          display: "Option 1"
        },
        {
          label: 2,
          display: "Option 2"
        },
        {
          label: 3,
          display: "Option 3"
        }
      ],
      radioVal: 1
    }
  }
}
</script>

<style>
#app {
  height:100%;
  width: 100%;
  position:absolute;
  font-family: "Asap",sans-serif;
}
body {
  margin:0px;
}
</style>
