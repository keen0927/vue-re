

<template>
  <div id="app" @contextmenu.prevent="ctxStop">
    <p>
      <input 
        id="textInput"
        type="text"
        :style="style1"
        @keyup.enter="deposit"
        @mouseover.stop="overEvent"
        @mouseout.stop="outEvent"
        v-model="amount">
    </p>
    <p v-show="isValidate === true">올바른 수를 입력하세요</p>
    <button id="deposit" @click="deposit()">예금</button>
    <button id="withdraw" @click="withdraw()">인출</button>
    <h3>계좌잔고 : {{balance}}</h3>
    <button id="btn1" :style="[myColor, myLayout]">스타일 버튼</button>
  </div>
</template>

<script>

export default {
  name: 'App',
  data: function(){
    return {
      amount: 0,
      balance: 0,
      isValidate: false,
      style1: {
        border: "2px solid olive",
        borderRadius: "4px",
        backgroundColor: "aqua"
      },
      myColor: {
        color: "blue"
      },
      myLayout: {
        padding: "20px"
      }
    }
  },
  methods: {
    overEvent() {
      this.style1.backgroundColor = "gray"
    },
    outEvent() {
      this.style1.backgroundColor = "aqua"
    },
    // deposit() {
    //   this.balance += parseInt(this.amount);
    //   this.amount = 0;
    // },
    // withdraw() {
    //   this.balance -= parseInt(this.amount);
    //   this.amount = 0;
    // }    
    deposit(e) {
      var amt = parseInt(this.amount);
      if (amt <= 0) {
        this.isValidate = true
        this.amount = 0;
        document.getElementById('#textInput');
      } else {
        this.balance += amt;
        this.isValidate = false;
      }
    },
    withdraw() {
      var amt = parseInt(this.amount);
      if (amt <= 0) {
        this.isValidate = true;
        this.amount = 0;
        document.getElementById('#textInput');
      } else {
        this.balance -= amt;
        this.isValidate = false;
      }
    },
    // ctxStop() {
    //   // e.preventDefault();
    //   console.log('111');
    // }
    ctxStop: function(e) {
      e.preventDefault();
    }
    
  },
}
</script>

<style lang="scss">

</style>
