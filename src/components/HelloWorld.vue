<template>
  <div class="hello">
    <input type="text" v-model="todo"/>
    <button @click="salvar()">Salvar</button>
  </div>
  <div>
    <ul>
      <li v-for="(item, index) in list" :key="index">
        {{ item }} <button @click="deleteItem(index)">X</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',

  data() {
    return {
      todo: "",
      list: []
    }
  },

  methods: {
    salvar() {
      this.list.push(this.todo)
      console.log("salvei", this.todo);
    },
 
    deleteItem(index) {
      console.log(index)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
