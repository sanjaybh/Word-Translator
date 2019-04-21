<template>
  <div id="app" class="text-center">
    <h1>Word Translate</h1>
    <h5>Powered by vue.js</h5>

    <TranslateForm @formSubmit="onFormSubmit"></TranslateForm>
    
    <TranslateOutput :translatedText="translatedText"></TranslateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm';
import TranslateOutput from './components/TranslateOutput';

export default {
  name: 'app',
  components: {
    TranslateForm, TranslateOutput
  },
  data: function(){
    return {
      translatedText: ''
    }
  },
  methods:{
    onFormSubmit:function(text, language){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20190421T054405Z.86aa4e28b6df0662.a9d74eebcea0a477f99f01948faa8f1ba89f4818&lang='+language+'&text='+text)
      .then(response => {
        this.translatedText = response.body.text[0];
      })
    }
  }
}
</script>

<style>
  body{
    background: #eee;
  }
</style>
