<template>
  <div id="TranslateForm">
    <form v-on:submit="submitForm">
      <input type="text"  v-model='textToTranslate' placeholder="Input your content here"/>
      <select v-model="language">
        <option value="en">English</option>
        <option value="zh">Chinese</option>
        <option value="my">Burmese</option>
        <option value="ja">Japanese</option>
      </select>
      <input type="submit" value="Translate">
    </form>
  </div>
</template>

<script>
  export default {
    name: 'TranslateForm',
    data: function () {
      return{
        textToTranslate: '',
        language: 'en'
      }
    },
    methods:{
      submitForm:function(e){
        this.$emit("formSubmit",this.textToTranslate,this.language)
        e.preventDefault();
      }
    }
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
