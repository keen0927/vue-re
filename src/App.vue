

<template>
  <div id="app">
    <p>이름 : <input type="text" v-model="name" placeholder="두자 이상 입력"></p>
    <table id="list">
      <thead>
        <tr>
          <th>번호</th>
          <th>이름</th>
          <th>전화번호</th>
          <th>주소</th>
        </tr>
      </thead>
      <tbody id="contacts">
        <tr v-for="contact in contactlist">
          <td>{{contact.no}}</td>
          <td>{{contact.name}}</td>
          <td>{{contact.tel}}</td>
          <td>{{contact.address}}</td>
        </tr>
      </tbody>
    </table>
    <div v-show="isProcessing === true">조회중</div>
    
  </div>
</template>

<script>

export default {
  name: 'App',
  data: function(){
    return {
      name: '',
      isProcessing: false,
      contactlist: []
    }
  },
  watch: {
    name: function(val) {
      if (val.length >= 2) {
        this.axiosContacts();
      } else {
        this.contactlist = [];
      }
    }
  },
  methods: {
    axiosContacts: _.debounce(function(){

    },1000);
  }
  
  


}
</script>

<style lang="scss">
#list {
  width: 400px;
  border: 1px solid #000;
  border-collapse: collapse;
  td, th {
    border: 1px solid #000;
    text-align: center;
  }
  thead > tr {
    color: yellow;
    background-color: purple;
  }
}
</style>
