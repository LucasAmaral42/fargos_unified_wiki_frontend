<template>
  <div class="item-div">
    <div class="image-div">
      <a class="item-url" v-bind:href="item.url">
        <img v-bind:src="item.image_url"/>
      </a>
    </div>
    <div class="item-info">
      <span class="item-name-types">
        <h4 class="item-name">{{ item.name }}</h4>
        <p class="item-types">(Types: {{ item.types.join(", ") }})</p>
      </span>
      <p class="item-description">{{ item.description }}</p>
    </div>
    <div class="item-button">
      <a class="item-url" v-bind:href="item.url">
        <span>Go to Wiki</span>
      </a>
    </div>
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
    margin: 1vh 0.3vw 0 0.3vw;
    padding: 1vh 0;
    width: 81vw;
  }

  .image-div {
    width: 15vw;
    margin: 0 15px;
    text-align: center;
  }

  .image-div img {
    align-self: flex-start;
    height: 4.5vh;
    max-width: 15vw;
    object-fit: cover;
  }

  .item-info {
    max-height: 8vh;
  }

  .item-name-types {
    display: flex;
    align-items: center;
  }

  .item-name{
    margin: 0;
    padding: 0;
  }

  .item-types {
    margin: 0 0.5vw;
    font-size: 0.8rem;
    font-weight: lighter;
  }

  .item-description {
    overflow: hidden;
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    max-width: 75ch;
    margin: 1rem 0 0 0;
  }

  .item-button {
    margin-left: auto;
    margin-right: 2vw;
  }

  .item-button span {
    background-color: #DADADA;
    border-radius: 5px;
    width: 15vw;
    padding: 1.1rem 6rem;
  }

  a, a:hover a:focus, a:active {
    text-decoration: none;
    cursos: inherit;
    color: black;
  }
</style>
