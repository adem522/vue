<template>
  <v-card>
    <v-tabs
      v-model="tab"
      background-color="primary"
      dark
    >
      <v-tab
        v-for="item in items"
        :key="item.tab"
      >
        {{ item.tab }}
      </v-tab>
    </v-tabs>

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
  </v-card>
</template>

<script>
import package1 from './packages/package1'
import package2 from './packages/package2'
import package3 from './packages/package3'
import package4 from './packages/package4'
import package5 from './packages/package5'
import package6 from './packages/package6'
  export default {
    components: {        
        package1,
        package2,
        package3,
        package4,
        package5,
        package6,
    },
    data () {
      return {
        tab: null,
        items: [
          { tab: 'One', content: 'package1' },
          { tab: 'Two', content: 'package2' },
          { tab: 'Three', content: 'package3' },
          { tab: 'Four', content: 'package4' },
          { tab: 'Five', content: 'package5' },
          { tab: 'Six', content: 'package6' },
        ],
      }
    },

  }
</script>