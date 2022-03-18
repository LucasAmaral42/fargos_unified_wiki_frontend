<template>
  <div class="search-div">
    <input type="text"
    class="search-input"
    v-on:input="$emit('name', $event.target.value)"
    placeholder="Search by Name">
  </div>
</template>

<script>
export default {

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .search-div {
    display: flex;
    width: 100%;
    height: 5vh;
    background-color: #FFFFFF;
    border-radius: 10px 10px 0 0;
    align-items: center;
    justify-content: flex-end;
  }

  .search-input {
    height: 3vh;
    width: 80vw;
    font-size: 20px;
    margin-right: 1vh;
    padding-left: 10px;
    border-radius: 10px;
    border: none;
    background-color: #E0D9D9;
  }
</style>
