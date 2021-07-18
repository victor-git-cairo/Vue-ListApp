<template>
  <div id="app" class="bg-gray-200 w-full h-screen flex flex-col items-center p-4">

   <input type="text" placeholder="Add an item" v-model="value" />

   <button @click.prevent="addItem">Add</button>               

   <List :items="items"></List>

  </div>
</template>

<script>
import List from './components/List'


export default {
  name: 'App',
  components: {
    List,
  },
  data() {
    return {
      value: '' ,
      items: [
        'item1', 
        'item2'
      ]
    }
  },
  methods: {
    addItem: function () {
      this.items.push(this.value);
      // this.items.unshift(this.item);
      this.value = '';
    }
  }
}
</script>

<style>
  @import './assets/styles.css';
  /* require('@/assets/styles/main.css') */
  /* https://stackoverflow.com/questions/43784202/how-to-include-css-files-in-vue-2 */

</style>
