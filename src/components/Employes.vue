<template>
  <div>
    <h1>Employees List will Render through API</h1>
    <br>
    <div class="cardgrid" >
  <b-card 
     v-for="data in products" :key="data.id"
    :title="data.title"
    :img-src="data.image"
    img-alt="Image"
    img-top
    tag="article"
    style="max-width: 12rem;"
    class="mb-2">
    <b-card-text> 
{{data.category}}
    </b-card-text>
    <small>{{ data.description }}</small>
    <b-button href  ="#" variant="primary"> Rs  {{ data.price }}</b-button>
  </b-card>
</div>

    
  </div>
</template>

<script>

// import bootstrapVue from '@/plugins/bootstrap-vue'
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";
Vue.use(VueAxios, axios);

export default {
  name: "EmployeesVue",
  data() {
    return {
      staff: undefined,
      products : undefined
    };
  },
  mounted() {
    Vue.axios
      .get("https://fakestoreapi.com/products")
      .then((res) => {
        // this.staff = res.data
        this.products = res.data
        console.table(res.data)
      })
      .catch((err) => console.log(err));
  },
};
</script>


<style>
.cardgrid {
  border: 2px solid black;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  width: 70vw;
  height: max-content;
  margin: 0 auto;
  padding: 10px;
}

.card {
  margin: 12px 12px;
}
</style>