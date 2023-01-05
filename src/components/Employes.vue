<template>
  <div>
    <h1>Employees List will Render through API</h1>

    <table border="2px solid black" >
        <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Username</th>
            <th>Email</th>
            <th>Phone</th>
        </tr>
        <tr v-for="data in staff" :key="data.id" >
            <td> {{ data.id }} </td>
            <td> {{ data.name }} </td>
            <td> {{ data.username }} </td>
            <td> {{ data.email }} </td>
            <td> {{ data.phone }} </td>

        </tr>
    </table>
    

    
  </div>
</template>

<script>

import bootstrapVue from '@/plugins/bootstrap-vue'
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";

Vue.use(VueAxios, axios);

export default {
  name: "EmployeesVue",
  data() {
    return {
      staff: undefined,
    };
  },
  mounted() {
    Vue.axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then((res) => {
        this.staff = res.data
      })
      .catch((err) => console.log(err));
  },
};
</script>
