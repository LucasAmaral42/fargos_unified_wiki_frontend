<template>
  <div class="item-div">
    <img src="https://static.wikia.nocookie.net/calamitymod_gamepedia_en/images/8/87/Ark_of_the_Ancients.png"/>
    <h4 class="">{{ item.name }}</h4>
  </div>
</template>

<script>
export default {
  props: ['item']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .item-div {
    align-items: center;
    background-color: #FFFFFF;
    border-radius: 10px;
    display: flex;
    height: 8vh;
    margin-top: 1vh;
    margin: 1vh 13px 0 13px;
    width: 79vw;
  }

  img {
    height: 70%;
    margin-left: 10px;
  }
</style>
