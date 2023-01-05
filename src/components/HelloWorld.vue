<template>
  <div class="hello">
    <!-- <h1 v-bind:class="ShowStyle ? 'head' : 'para'">{{ message }}</h1> -->
    <h1 v-bind:style="{ color: 'purple' }">{{ message }}</h1>
    <!-- <ButtonCompVue age="18" /> -->
    <!-- <EmployesVue /> -->
    <!-- <calenderVue /> -->
    <PostVue />
    <UserDataVue />
  </div>
</template>

<script>
// import calenderVue from './calender.vue';
// import ButtonCompVue from "./ButtonComp.vue";
// import EmployesVue from "./Employes.vue";
import PostVue from './Post.vue';
import UserDataVue from './UserData.vue';
export default {
  name: "HelloWorld",
  methods: { 
    checkTitle(val) {
      this.message = val;
    },
  },
  components: {
    // ButtonCompVue,
    // EmployesVue ,
    // calenderVue , 
    PostVue ,
    UserDataVue
  
  },
  props: {
    msg: String,
  },
  data() {
    return {
      ShowStyle: true,
      message: "Jetnetix Solutions",
      userData : [
        {name : 'Sualeh' , id : '001' , company : 'xyz'},
        {name : 'Sufiyan' , id : '002' , company : 'xyz'},
        {name : 'Sultan' , id : '003' , company : 'xyz'},
        {name : 'Shahzain' , id : '004' , company : 'xyz'},

      ]
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.head {
  color: red;
  font-weight: bold;
}

.para {
  color: blue;
  font-weight: 300;
}
</style>
