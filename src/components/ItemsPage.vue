<template>
  <div class="body">
    <SearchBar @name="getName"/>
    <section class="results-section">
      <FilterSideBar/>
      <div class="item-results">
        <ItemLine class="item-line" v-for="item in FilteredItems" :key="item._id" :item="item"/>
      </div>
    </section>
  </div>
</template>

<script>
import SearchBar from './navbar/SearchBar.vue'
import FilterSideBar from './navbar/FilterSideBar.vue'
import ItemLine from './ItemLine.vue'
import axios from 'axios';

export default {

  components: {
    SearchBar,
    FilterSideBar,
    ItemLine
  },

  data(){
    return{
      items : [],
      name : '',
      filters: [],
      mods: []
    }
  },

  created(){
    axios
      .get('http://localhost:3000/')
      .then(res => (this.items = res.data))
  },

  computed: {
    FilteredItems(){
      if (this.name) {
        let exp = new RegExp(this.name.trim(), 'i');
        return this.items.filter(item => exp.test(item.name)).slice(0,200);
      } else{
        return this.items.slice(0,200);
      }
    }
  },

  methods: {
    getName(value) { this.name = value.toLowerCase(); }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .results-section {
    display: flex;
  }

  .item-results {
    display: flex;
    flex-direction: column;
    overflow-y: scroll;
    height: 88vh
  }
</style>
