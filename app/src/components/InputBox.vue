<template>
  <div id='idTextAreaDiv'>
    <div >
      <textarea
        :placeholder="PlaceHolderText"
        id="idTextArea"
        cols="30"
        rows="10"
        v-model="Quote"
      ></textarea>
    </div>
    <div>
      <button id="idSubmitBtn" @click.prevent="onPressQuoteSubmit">Submit</button>
    </div>
  </div>
</template>
<script>
//import { QuoteBus } from "../main";
export default {
  data() {
    return {
        Quote: "",
        Quotes: [],
        PlaceHolderText: "Fill this world with beautiful words..."
    };
  },

  methods: {
      onPressQuoteSubmit() {
          if(this.Quote){
            this.$emit('newQuoteAdded', this.Quote);
            this.Quote = '';
            //this.Quotes.push(this.Quote);
            //QuoteBus.$emit('text',this.Quotes);
          }else{
            alert("Looks like you forgot write something..??")
          }
          
      }
  }
};
</script>
<style scoped>
#idTextArea {
  width: 50rem;
  height: 10rem;
  font-family:fantasy;
  
}
#idSubmitBtn{
    width: 10rem;
    height: 2rem;
    border-radius: 5px;
    background-blend-mode: color-burn;
    background-color: aliceblue;
    display: inline-block;
    font-family:fantasy;
    overflow: hidden;
}

#idSubmitBtn:hover{
background-color:lightskyblue;
}

#idSubmitBtn:focus{
  outline: none;
  overflow: hidden;
}

#idTextAreaDiv{
    text-align: center;
}

</style>