

<template>
  <div id="app" @contextmenu.prevent="ctxStop">
    <p><input id="textInput" type="text" @keyup.13="deposit" v-model="amount"></p>
    <p v-show="isValidate === true">올바른 수를 입력하세요</p>
    <button id="deposit" @click="deposit()">예금</button>
    <button id="withdraw" @click="withdraw()">인출</button>
    <h3>계좌잔고 : {{balance}}</h3>
  </div>
</template>

<script>

export default {
  name: 'App',
  data: function(){
    return {
      amount: 0,
      balance: 0,
      isValidate: false
    }
  },
  methods: {
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
