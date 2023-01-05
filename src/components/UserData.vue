<template>
  <div>
    <b-table hover :items="items"></b-table>
  </div>
</template>

<script>
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";

Vue.use(VueAxios, axios);

export default {
  name: "UserData",
  data() {
    return {
      items: [
      { first_name: 'Dickerson', email: 'Macdonald' }
      ],
    };
  },


  mounted() {
    this.axios.get('http://localhost:3000/users')
    .then((res)=>{
        console.log(res.data)
        this.items = res.data
    })
    .catch((err)=>{
        console.log(err)
    })
  },
};
</script>
