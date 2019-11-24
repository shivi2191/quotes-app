<template>
  <div class="container">
    <ProgressBar></ProgressBar>
    <InputBox @newQuoteAdded="newQuote"></InputBox>
    <div class="container">
      <QuoteTiles :QuoteText="Quotes" @clickedItem="deleteClickedItem"></QuoteTiles>
      <div class="row customMargin">
        <div class="col-sm-12 text-center">
          <div class="alert alert-info">Info: Click on the tile to delete it!</div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import ProgressBar from "../components/ProgressBar";
import InputBox from "../components/InputBox";
import QuoteTiles from "../components/QuoteTiles";
import { QuoteBus } from "../main";
export default {
  data() {
    return {
      comp: "",
      Quotes: [],
      arrLength: "",
      dummyArray: []
    };
  },
  components: {
    ProgressBar: ProgressBar,
    InputBox: InputBox,
    QuoteTiles: QuoteTiles
  },
  methods: {
    newQuote(Text) {
      this.dummyArray.push(Text);
      this.arrLength = this.dummyArray.length;

      if (this.arrLength <= 10) {
        this.Quotes.push(Text);
        QuoteBus.$emit("arrLength", this.arrLength);
      } else {
        alert("Maximum Limit of Quotes Reached!");
      }
    },
    deleteClickedItem(index) {
      if (!isNaN(index)) {
        this.Quotes.splice(index, 1);
        this.dummyArray.splice(index, 1);
        this.arrLength = this.Quotes.length;
        QuoteBus.$emit("arrLength", this.arrLength);
      }
    }
  }
};
</script>
<style scoped>
.customMargin {
  margin: 50px;
}
</style>