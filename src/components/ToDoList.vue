<template>
  <h1>Todo List</h1>
  <div class="hello">
    <input type="text" v-model="todo" placeholder="Nova tarefa"/>
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
  name: 'ToDoList',

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
      this.list.splice(index)
      console.log(index)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  margin-bottom: 50px;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: list-item;
  margin: 0 10px;
}

button {
  background-color: aqua;
}
</style>
