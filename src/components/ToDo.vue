.<template>

  <div class="container">

    <h1>TODO LIST IN VUE JS </h1>

    <div  v-if="!isEdit">
      <input  type="text" v-model="Todo">

      <input type="submit" value="Add" @click="AddToList"><br>

    </div>

    <div  v-else>
      <input  type="text" v-model="Todo"><br><br>
      <input type="submit" value="Update" @click="updatelist"><br>
    </div>

    <ol>

      <li v-for="(Todo, index) in todos" :key="index">
        {{ Todo }}<br>
        <button @click="editList(index, Todo)">Edit</button> &nbsp;  &nbsp;
        <button @click="removeFromList(index)">Delete</button>
      </li>
    </ol>


  </div>

</template>

<script>

export default {
  name: 'ToDo',

  data(){
    return{
      isEditing: false,
      Todo: '',
      todos: [],
      selectedTodo: null
    }

  },

  methods: {

    AddToList() {
      this.todos.push(this.Todo)
      this.Todo = ''
    },

    removeFromList(index) {
      this.todos.splice(index, 1)
    },

    updatelist() {
      this.todos.splice(this.selectedIndex, 1, this.Todo)
      this.Todo = ''
      this.isEdit = false
    },

    editList(index, Todo) {
      this.isEdit = true
      this.Todo = Todo
      this.selectedIndex = index
    }
  }
}
</script>
<style>

h1 {
  padding-top: 45px;
}


body{
  background-color: #85FFBD;
  background-image: linear-gradient(45deg, #85FFBD 0%, #FFFB7D 100%);

}



.container{
  max-width: 800px;
  margin: auto;
  padding: 15px;
  font-family: "montserrat",sans-serif;
  box-sizing: border-box;
}

</style>