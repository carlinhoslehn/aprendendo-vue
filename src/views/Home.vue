<template>
  <div class="home">
    <h1> Arquivo de template</h1>
    <ListaPost :info="info" />
  </div>
</template>

<script>

import ListaPost from '@/components/ListaPost.vue'
import axios from 'axios';

export default {
  name: 'Home',
  components: {
    ListaPost,
  },
  data(){
    return {
      info: []
    }
  },
  mounted: function () {
      this.readJson()
  },
  methods: {
       async readJson() {
           await axios.get('/json/banner.json')
           .then( response => (this.info = response.data));
       }
  }
}
</script>
