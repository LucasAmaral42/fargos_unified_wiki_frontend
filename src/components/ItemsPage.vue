<template>
  <div class="body">
    <SearchBar @name="getName"/>

    <section class="results-section">
      <FilterSideBar @types="getTypes" @mods="getMods"/>

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

  data() {
    return{
      items : [],
      name : '',
      types: [],
      mods: []
    }
  },

  created() {
    axios
      .get("http://localhost:3000/")
      .then(response => (this.items = response.data))
  },

  watch: {
    'types': function (val, ) {
      axios
        .get("http://localhost:3000/", { params: { types: val, mod: this.mods } })
        .then(response => (this.items = response.data))
    },
    'mods': function (val, ) {
      axios
        .get("http://localhost:3000/", { params: { types: this.types, mod: val } })
        .then(response => (this.items = response.data))
    }
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
    getName(value) { this.name = value.toLowerCase(); },
    getTypes(value) { this.types = value },
    getMods(value) { this.mods = value }
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
    align-items: center;
    overflow-y: scroll;
    height: 87.5vh;
    width: 84vw;
  }
</style>
