

<template>
  <div id="app">
    <!-- <h2 v-text="this.data.message"></h2> -->
    <h2 v-text="message">H2 문맥입니다</h2>
    <h5>SUM : {{sum}}</h5>
    <h5>GET : {{amount}}</h5>
    
    <h4># methods SUM</h4>
    <input type="text" v-model="num">
    <p>1부터 입력된 수까지의 합 : <span>{{sum}}</span></p>
    <h5>SUM : {{sumNumber()}}</h5>
    <h5>SUM : {{sumNumber()}}</h5>
    <h5>SUM : {{sumNumber()}}</h5>
    <h4># computed SUM</h4>
    <h5>SUM : {{sum}}</h5>    
    <h5>SUM : {{sum}}</h5>    
    <h5>SUM : {{sum}}</h5> 

    <h6>관찰속성</h6> 
  </div>
</template>

<script>



export default {
  name: 'App',
  data: function(){
    return {
      message: '니호호호',
      num: 5,
      amt: 123456666,
      number: 0
    }
  },
  computed: {
    sum() {
      console.log(Date.now());
      var n = Number(this.num);
      if ( n < 1) return 0;
      return ((1+n) * n) / 2;
    },
    amount: {
      get() {
        let s = new String(""+this.amt);
        let result = "";
        let num = 0;
        for (let i = s.length -1 ; i >= 0 ; i--) {
          result = s[i] + result;
          if ( num % 3 === 2 && i !== 0)
            result = ',' + result;
            num++;
        }
        return result;
      },
      set() {
        if (typeof(amt) === "string") {
          let result = parseInt(amt.replace(/,/g,""))
          if (isNaN(result)) {
            this.amt = 0;
          } else {
            this.amt = result;
          }
        } else if (typeof(amt) === "number") {
          this.amt = amt;
        }
      }
    }
  },
  methods: {
    sumNumber() {
      console.log("메소드 SUM : ",Date.now());
      let n = Number(this.number)  ;
      if ( n === 0 ) return 0;
      if ( Number.isNaN(n) || n < 1 ) return "숫자를 입력하세요";
      return ((1 + n) * n) / 2;
    }
  },
  


}
</script>

<style lang="scss">
$black: red;

#app {
  border: 1px solid $black;
}
</style>
