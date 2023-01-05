<template>
  <div>
    <button @click="counter = counter + 1">{{ counter }}</button>
    <h3>Fetch API Data</h3>
    <li v-for="key in names" :key="key.id">
      {{ key.name }} {{ key.id }} {{ key.company }}
    </li>
  </div>
</template>
<script>

import axios from "axios";
import VueAxios from "vue-axios";
import Vue from "vue";
// import bootstrapVue from '@/plugins/bootstrap-vue'
// fetch('https://jsonplaceholder.typicode.com/todos')
// .then((res)=>console.log(res))

export default {
  name: "ButtonComp",
  props: ["names", "age"],

  beforeCreate() {
    console.log(this.class);
  },
  created() {
    console.log(this.class);
  },
  beforeMount() {
    console.log(this.class);
  },
  mounted() {
    this.class = "82";
    console.log(this.class);
    Vue.use(VueAxios, axios);
    Vue.axios
      .get("https://jsonplaceholder.typicode.com/todos")
      .then((res) => console.log(res.data[0].title))
      .catch((err) => console.log(err));
  },
  beforeUpdate() {
    console.log("Before Update called");
  },
  updated() {
    console.log("Updated Hook");
  },

  data() {
    return {
      person: "Male",
      class: "any number",
      counter: 0,
    };
  },
  methods: {
    update: function () {
      console.log("Update Clicked");
    },
  },
};
</script>
