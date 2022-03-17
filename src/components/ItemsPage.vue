<template>
  <div class="body">
    <SearchBar @name="getName"/>
    <section class="results-section">
      <FilterSideBar/>
      <div class="item-results">
        <ItemLine class="item-line"/>
      </div>
    </section>
  </div>
</template>

<script>
import SearchBar from './navbar/SearchBar.vue'
import FilterSideBar from './navbar/FilterSideBar.vue'
import ItemLine from './ItemLine.vue'

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

  // created(){
  //   this.$http.get('http://localhost:3000/')
  //     .then(res => res.json())
  //     .then(items => this.items = items, err => console.log(err))
  // },

  computed: {
    FilteredItems(){
      console.log(this.name)
      if (this.name) {
        let exp = new RegExp(this.name.trim(), 'i');
        return this.items.filter(item => exp.test(item.name));
      } else{
        return this.items;
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
    overflow-y: scroll
  }
</style>
