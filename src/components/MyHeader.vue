<template>
  <header>
    <h1>BOOLFLIX</h1>
    <div>
        <input v-model.trim="text" type="text">
        <button @click.prevent="$emit('search', text)">search</button> 
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
      h1 {
        color: red;
      }

      input {
        height: 30px;
        margin-right: 25px;
      }
  }
</style>