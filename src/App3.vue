

<template>
  <div id="app">
    x: <input type="text" v-model="x"><br />
    y: <input type="text" v-model="y"><br />
    Sum : {{sum}}

    
  </div>
</template>

<script>



export default {
  name: 'App',
  data: function(){
    return {
      x: 0,
      y: 0,
      sum: 0  
    }
  },
  watch: {
    x(v) {
      console.log("X 변경");
      let result = Number(v) + Number(this.y);
      if (isNaN(result)) this.sum = 0;
      else this.sum = result;
    },
    y(v) {
      console.log('Y 변경');
      this.y = v;
      var result = Number(this.x) + Number(v);
      if (isNaN(result)) this.sum = 0;
      else this.sum = result;
    }
  }
  
  


}
</script>

<style lang="scss">
$black: red;

#app {
  border: 1px solid $black;
}
</style>
