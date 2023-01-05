<template>
    <b-row>
      <b-col md="auto">
        <b-calendar v-model="value" @context="onContext" locale="en-US"></b-calendar>
      </b-col>
      <!-- <b-col>
        <p>Value: <b>'{{ value }}'</b></p>
        <p class="mb-0">Context:</p>-->
        <pre class="small">{{ context}}</pre>
      <!-- </b-col> --> -->
    </b-row>
  </template>
  
  <script>
    export default {
        name:'CalenderVue',
      data() {
        return {
          value: '',
          context: null
        }
      },
      methods: {
        onContext(ctx) {
          this.context = ctx
        }
      },
      mounted() {
        setTimeout(() => {
            console.log(this.context.activeDate)
        }, 4000);
      },
      updated() {
          console.log(this.context.activeDate)
      },
    }
  </script>