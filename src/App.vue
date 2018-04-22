<template>
  <div id="app">
    <h1>Aemple---在线翻译</h1>
    <h5 class="text-muted">简单 / 易用 / 便捷</h5>
   <translateForm v-on:formSubmit="translateText"></translateForm>
   <translateOutput v-text="translatedText"></translateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'
export default {
  name: 'App',
  data:function() {
    return{
      translatedText:''
    }
  },
  components: {
    TranslateForm,TranslateOutput
  },
  methods:{
    translateText:function(text,language) {
      // alert(text);
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180422T051551Z.492b76dd1773d2bf.c9abe7fb8dfd968a49475e47c1d7aef7d70a5cb4&lang='+language+'&text='+text)
      .then((Response)=>{
        // console.log(Response.body.text[0]);
        this.translatedText = Response.body.text[0];
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

h1 {
   margin-left: 80px;
    font-size: 80px;
  	color: #fff;
		text-shadow: 0 1px 0 #ccc, 0 2px 0 #c9c9c9, 0 3px 0 #bbb, 0 4px 0 #b9b9b9, 0 5px 0 #aaa, 0 6px 1px rgba(0,0,0,0.1), 0 0 5px rgba(0,0,0,0.1),0 1px 3px rgba(0,0,0,0.3),0 3px 5px rgba(0,0,0,0.2),0 5px 10px rgba(0,0,0,0.25);
}

h5 {
  margin-left: 80px;
  font-size: 25px;
  color: #FFFFFF;
  text-shadow: 0 -1px 0 #374683;
  margin-bottom: 40px;
}

h2 {
  font-size: 40px;
  color: #c00;
  -webkit-text-stroke: 1px #000;
}
</style>
