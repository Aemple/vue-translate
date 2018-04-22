<template>
  <div class="row"  id="translateForm">
    <div class="col-md-5 col-md-offset-4">
      <form class="form-inline" id="transForm"  v-on:submit="formSubmit">
        <div class="form-group">
          <label class="sr-only" for="exampleInputAmount">请输入需要翻译的内容</label>
            <div class="input-group">
             <div class="input-group-addon">@</div>
             <input type="text" v-model="textToTranslate" class="form-control input-lg" id="exampleInputAmount" placeholder="请输入需要翻译的内容">
           </div>
        </div>
        <!-- <input class="form-control " type="text" v-model="textToTranslate" placeholder="输入需要翻译的内容"> -->
        <select class="form-control input-lg" v-model="language">
          <option value="en">English</option>
          <option value="ru">Russian</option>
          <option value="ko">Korean</option>
          <option value="ja">Janpenese</option>
        </select>
        <input class="btn btn-success btn-lg" type="submit" value=" 翻 译 ">
      </form>
    </div>
  </div>

</template>

<script>


export default {
  name: 'translateForm',
  data:function(){
    return {
      textToTranslate:"",
      language:""
    }
  },
  methods: {
    formSubmit:function(e){
      // alert(this.textToTranslate);
      this.$emit("formSubmit",this.textToTranslate,this.language);
      e.preventDefault();
    }
  },
  created:function(){
    this.language = "en";
  }
}
</script>

<style>
    /* #transForm{
      border-radius: 10px;
      border: 1px #ccc solid;
    } */
</style>
