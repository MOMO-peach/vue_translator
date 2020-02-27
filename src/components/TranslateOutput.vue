<template>
  <div id="TranslatOutput">
    <h2>{{translatedText}}</h2>
  </div>
</template>

<script>
  export default {
    name: 'TranslateOutput',
    props:[
      'translatedText'
    ]
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
