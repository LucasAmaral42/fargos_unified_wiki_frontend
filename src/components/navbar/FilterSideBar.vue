<template>
  <div class="filter-div">
    <div class="types-menu">
      <h1>Types</h1>

      <v-select
        multiple
        v-model="filter"
        :options="filters">
      </v-select>
    </div>

    <div class="mods-menu">
      <h1>Mods</h1>

      <v-select
        multiple
        v-model="mod"
        :options="mods">
      </v-select>
    </div>
  </div>
</template>

<script>
import vSelect from "vue-select";

export default {
  components: {
    vSelect
  },

  data(){
    return{
      items : [],
      name : '',
      filters: [
        "",
      ],
      mods: [
        "Calamity",
        "Dragon Ball Terraria",
        "Shadows of Abaddon",
        "Thorium"
      ]
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .filter-div {
    display: flex;
    height: calc(100vh - 139px);
    width: 15vw;
    background-color: #FFFFFF;
    flex-direction: column;
    padding: 0 15px;
  }

  .types-menu {
    margin-bottom: 30px;
  }

  ul li {
    list-style-type: none;
    color: #D0D0D0;
    margin-bottom: 10px;
  }

  ul {
    padding-left: 15px;
  }

  v-select {
    padding-right: 5px;
  }
</style>
