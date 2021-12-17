<template>
  <header>
    <h1>BOOLFLIX</h1>
    <div>
        <i class="fas fa-search" @click.prevent="$emit('search', text)"></i>
        <input v-model.trim="text" type="text" @keyup.enter="$emit('search', text)" placeholder="search">
    </div>
  </header>
</template>

<script>

export default {
  name: 'MyHeader',
  
  data() {
    return {
      text: "",
    };
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  header {
    background-color: rgba(0, 0, 0, 0.876);
    display: flex;
    justify-content: space-between;
    padding: 10px;
    height: 55px;
      h1 {
        color: red;
        user-select: none;
      }

      input {
        height: 30px;
        margin: 0 20px;
      }

      i {
        font-size: 25px;
        position: relative;
        top: 5px
      }
  }
</style>