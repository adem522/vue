<template>
  <v-card>
    <demo-sign-modal />
    <v-toolbar
      color="purple darken-4"
      dark
      flat
    >    
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
        v-model="tab"     
        fixed-tabs
        slider-color="white"
      >
        <v-tab
          v-for="item in items"
          :key="item.tab"
        >
          {{ item.tab }}
        </v-tab>
        <v-tabs-items v-model="tab">
            <v-tab-item
              v-for="item in items"
              :key="item.tab"
            >
              <v-card flat>          
                  <component v-bind:is="item.content"></component>           
              </v-card>
            </v-tab-item>
          </v-tabs-items>
        </v-tabs>
      </template>
    </v-toolbar>
  </v-card>
</template>

<script>
  import DemoSignModal from './components/SignIn.vue'
  import denemeTab from './components/denemeTab.vue'
  import denemeHome from './components/denemeHome.vue'
  export default {
    name: "App",
    components:{
      DemoSignModal,
      denemeTab,
      denemeHome
  },
  data () {
      return {
        tab: null,
        items: [
          { tab: 'Home', content: 'denemeHome' },
          { tab: 'Packages', content: 'denemeTab' },
          { tab: 'About', content: 'denemeHome' },
          { tab: 'Help', content: 'denemeHome' },
        ],
      }
    },
  methods: {
      accountClick() {          
        this.$modal.show('demo-sign')
      },
    },
  };
</script>