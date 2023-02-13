<template>
  <div id="SearchBar">
    <input type="search" name="search-bar" id="search-bar" placeholder="Search">
    <button type="submit" id="search-button"><IconSearch /></button>
  </div>
</template>

<script lang="ts">
import IconSearch from './icons/IconSearch.vue'

export default {
  name: 'Header',
  components: {
    IconSearch,
  },
}

</script>

<style scoped>
/* * {
  outline: auto;
} */

#SearchBar {
  width: 100%;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px
}

#search-bar {
  width: 100%;
  height: 100%;
  border: 0px solid white;
  border-radius: 100px;
  outline: none;
  background-color: rgb(46, 47, 48);
  color: rgb(245, 245, 245);
  padding: 25px;
  font-size: 14px;
  box-shadow: 0px 5px 30px 0px rgb(0, 0, 0);
  transition: all 0.25s ease;
}

#search-bar:focus {
  border: 2px solid rgb(48, 71, 94);
}

#search-button {
  width: 50px;
  height: 50px;
  border: none;
  border-radius: 50%;
  background-color: rgb(240, 84, 84);
  box-shadow: 0px 10px 15px -3px rgb(255, 0, 0);
}
</style>
