<template>
  <div id="app">
    <TranslateForm v-on:formSubmit="textTranslate"></TranslateForm>
    <TranslateOutput v-text="translatedText"></TranslateOutput>
  </div>
</template>

<script>
  import TranslateForm from "./components/TranslateForm";
  import TranslateOutput from "./components/TranslateOutput";
export default {
  name: 'App',
  data:function(){
    return{
      translatedText:''
    }
  },
  components: {TranslateForm,TranslateOutput},
  methods:{
    textTranslate:function (text,language) {
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20200227T065046Z.83fbabef44354634.c73e80fe11151c58b58cb38507ae7473e7ae7902&lang='+language+'&text='+text).then((res)=>{
        console.log(res.body['text'][0]);
        this.translatedText = res.body['text'][0];
      })
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
