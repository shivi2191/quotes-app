<template>
  <div id="idHeaderDiv">
    <div>
      <H3 id="idHeaderText">{{HeaderText}}</H3>
    </div>
    <div class="progress" id="idProgressBar">
      <div
        class="progress-bar"
        role="progressbar"
        aria-valuenow="70"
        aria-valuemin="0"
        aria-valuemax="100"
        :style="{width:width+'0' +'%'}"
      >{{width}}/10</div>
    </div>
  </div>
</template>
<script>
import { QuoteBus } from '../main';
export default {
  data() {
    return {
      HeaderText: "Welcome to Quotes Application",
      width: 0
    };
  },
  created(){
    QuoteBus.$on('arrLength', (arrLength)=>{
          this.width = arrLength;
        
    })
  }
};
</script>
<style scoped>
@import url("https://www.w3schools.com/w3css/4/w3.css");

#idProgressBar {
  margin: 10px 100px 75px 100px;
  border: 2px solid black;
  border-radius: 5px;
}

#idHeaderText {
  margin: 1px 10px 2px 100px;
  font-family: fantasy;
}

#idHeaderDiv {
  text-align: left;
}

.progress-bar {
    float: left;
    width: 0%;
    height: 100%;
    font-size: 12px;
    line-height: 20px;
    color:black;
    text-align: center;
    background-color: #337ab7;
    -webkit-box-shadow: inset 0 -1px 0 rgba(0,0,0,.15);
    box-shadow: inset 0 -1px 0 rgba(0,0,0,.15);
    -webkit-transition: width .6s ease;
    -o-transition: width .6s ease;
    transition: width .6s ease;
}
</style>