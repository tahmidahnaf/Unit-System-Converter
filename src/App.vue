<template>
  <div id="app">
    <div class="title">Unit System Converte'</div>

    <div class="container">
      <textField
        placeHolder="px"
        v-model.number="pxValue"
        @input="pxFunc(pxValue)"
      />
      <textField
        placeHolder="vh"
        v-model.number="vhValue"
        @input="vhFunc(vhValue)"
      />
      <textField
        placeHolder="vw"
        v-model.number="vwValue"
        @input="vwFunc(vwValue)"
      />
      <btn class="btn" @click.native="clearValue()">Clear</btn>
    </div>
  </div>
</template>

<script>
import textField from "./components/text-field";
import btn from "./components/btn";

export default {
  name: "App",
  components: {
    textField,
    btn,
  },
  data() {
    return {
      pxValue: NaN,
      vhValue: NaN,
      vwValue: NaN,
    };
  },
  methods: {
    pxFunc(v) {
      this.vhValue =
        Math.round(((100 * v) / window.innerHeight) * 100) / 100 || NaN;
      this.vwValue =
        Math.round(((100 * v) / window.innerWidth) * 100) / 100 || NaN;
    },
    vhFunc(v) {
      this.pxValue =
        Math.round(((window.innerHeight * v) / 100) * 100) / 100 || NaN;
      this.vwValue =
        Math.round(((100 * this.pxValue) / window.innerWidth) * 100) / 100 ||
        NaN;
    },
    vwFunc(v) {
      this.pxValue =
        Math.round(((window.innerWidth * v) / 100) * 100) / 100 || NaN;
      this.vhValue =
        Math.round(((100 * this.pxValue) / window.innerHeight) * 100) / 100 ||
        NaN;
    },
    clearValue() {
      this.pxValue = NaN;
      this.vhValue = NaN;
      this.vwValue = NaN;
    },
  },
};
</script>







<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Manrope");

body {
  font-family: "Manrope", sans-serif;
  background: #ffeaa7;
}
*::selection {
  background: rgba($color: #f8a5c2, $alpha: 0.4);
  box-sizing: border-box;
}
.title{
  background: #ffeaa7;
  box-shadow:  5px 5px 10px #d9c78e,
             -5px -5px 10px #ffffc0;
  height: 50px;
  width: 30vw;
  word-spacing: 20px;
  letter-spacing: 1px;
  border-radius: 5px;
  position: absolute;
  top: 40px;
  left: 50%;
  transform: translate(-50%);
  text-align: center;
  padding-top: 10px;
  font-size: 25px;


  @media screen and (max-width: 1120px) {
    font-size: 23px;
  }
  @media screen and (max-width: 1000px) {
    font-size: 20px;
  }
  @media screen and (max-width: 920px) {
    font-size: 18px;
  }
  @media screen and (max-width: 830px) {
    font-size: 20px;
    width: 40vw;
  }
  @media screen and (max-width: 700px) {
    font-size: 18px;
  }
  @media screen and (max-width: 620px) {
    font-size: 19px;
    width:56vw;
  }
  @media screen and (max-width: 470px) {
    font-size: 18px;
    width:65vw;
  }
  @media screen and (max-width: 380px) {
    font-size: 17px;
    width:70vw;
  }
}
.container {
  height: 300px;
  width: 36.6vw;
  background: #ffeaa7;
  position: absolute;
  box-shadow: inset 5px 5px 10px #d9c78e, inset -5px -5px 10px #ffffc0;
  border-radius: 10px;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  padding-left: 30px;

  @media screen and (max-width: 1050px) {
    width: 45vw;
  }
  @media screen and (max-width: 750px) {
    width: 55vw;
  }
  @media screen and (max-width: 570px) {
    width: 70vw;
  }
  @media screen and (max-width: 480px) {
    width: 85vw;
  }
  @media screen and (max-width: 370px) {
    height: 350px;
  }

  .btn {
    position: relative;
    top: 20px;

    // @media screen and (max-width: 630px) {
    //   right: -270px;
    // }
    @media screen and (max-width: 370px) {
      top: 40px;
    }
  }
}
</style>
