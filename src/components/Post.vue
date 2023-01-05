<template>
    <div>
      <b-form @submit="onSubmit" method="post">
        <b-form-group
          id="input-group-1"
          label="Email address:"
          label-for="input-1"
          description="We'll never share your email with anyone else."
        >
          <b-form-input
            id="input-1"
            v-model="users.email"
            type="email"
            placeholder="Enter email"
            required
          ></b-form-input>
        </b-form-group>
  
        <b-form-group id="input-group-2" label="Your Name:" label-for="input-2">
          <b-form-input
            id="input-2"
            v-model="users.name"
            placeholder="Enter name"
            required
          ></b-form-input>
        </b-form-group>
        <b-button type="submit" variant="primary">Submit</b-button>
      </b-form>
   
    </div>
  </template>
  
  <script>

import Vue from 'vue'
import VueAxios from 'vue-axios'
import axios from 'axios'

Vue.use(VueAxios , axios)
    export default {
        name : 'PostData',
      data() {
        return {
          users: {
            email: null,
            name: null
          },
          show: true
        }
      },
      methods: {
        onSubmit(event) {
          event.preventDefault()
        //   alert(JSON.stringify(this.users))
        this.axios.post('http://localhost:3000/users',this.users)
        .then(()=>console.warn('Send Data in API'))
        .catch((err)=>console.log(err))
        }
      },
 
    }
  </script>