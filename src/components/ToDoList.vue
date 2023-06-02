<template>
  <h1>Todo List</h1>
  <div class="hello">
    <input type="text" v-model="todo" placeholder="Nova tarefa"/>
    <button @click="salvar()">Salvar</button>
  </div>
  <div>
    <h1>Não Completa</h1>
    <ul>
      <li v-for="(item, index) in list" :key="index">
        {{ item }} <button @click="deleteItem(index,item)">X</button>
      </li>
    </ul>
  </div>
  <div>
    <h1>Completas</h1>
    <ul>
      <li v-for="(item, index) in todoCompleta" :key="index"> {{ item }}
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
      list: [],
      todoCompleta: []
    }
  },

  methods: {
    salvar() {
      this.list.push(this.todo)
      console.log("salvei", this.todo);
    },
 
    deleteItem(index,item) {
      this.list.splice(index,1)
      this.todoCompleta.push(item)
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
