<template>
  <div id="translateOutput">
    <h2>{{translatedTex}}</h2>
  </div>
</template>

<script>


export default {
  name: 'translateOutput',
  props:[
    "translatedText"
  ]

}
</script>

<style>
#translateOutput {
  margin-left: 50px;
  margin-top: 30px;
  font-size: 45px;
  color: #c00;
  -webkit-text-stroke: 1px #000;
}
</style>
