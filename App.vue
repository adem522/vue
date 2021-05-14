<template>
  <v-card>
    <v-toolbar
      color="purple darken-4"
      dark
      flat
    >
    <demo-sign-modal />
      <v-toolbar-title>Eight-Sup</v-toolbar-title>
      <v-spacer></v-spacer>      
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon v-on:click="accountClick">mdi-account</v-icon>
      </v-btn>
      <template v-slot:extension>
        <v-tabs          
          fixed-tabs
          slider-color="white"
        >
          <v-tab>
            Home
          </v-tab>
          <v-tab>
            Packages
          </v-tab>
          <v-tab>
            Help 
          </v-tab>
          <v-tab>
            Blog          
          </v-tab>          
        </v-tabs>
      </template>
    </v-toolbar>
  </v-card>
</template>

<script>
  import DemoSignModal from './components/SignIn.vue'
  export default {
    name: "App",
    components:{
      DemoSignModal,
  },
  methods: {
          accountClick() {          
            this.$modal.show('demo-sign')
      },
    },};
</script>
