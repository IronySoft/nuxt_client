<template>
  <div class="container">

    <div class="row">
      <form class="col-md-6 offset-3" @submit.prevent="addTodo">
        <input class="custom-checkbox" type="checkbox" @click="selectAll">

        <input class="form-control" type="text" placeholder="What needs to be done?" v-model="newText" required>

      </form>
    </div>
    <div class="row">

      <div class="col-md-6 offset-3">
        <ul class="list-group bg-danger">
          <li class="list-group-item" v-for="(todo,i) in filteredTodos" :key="i">
            <div class="row">
              <div class="col-md-2">
                <input class="btn btn-info" type="checkbox" v-model="todo.completed">

              </div>
              <div class="col-md-8">
                <label class="col-form-label-lg">{{todo.text}}</label>

              </div>
              <div class="col-md-2">
                <button class="table-hover btn btn-danger" @click="removeTodo(i)">x</button>

              </div>
            </div>


          </li>
        </ul>
        <p>{{remainingTodo}} Todo Left</p>
        <button @click="visibility='all'">All</button>
        <button @click="visibility='active'">Active</button>
        <button @click="visibility='completed'">Completed</button>

        <!--<button v-if="">Clear Completed</button>-->
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Calculation",
    data() {
      return {
        todos: [
          {
            text: 'abcd', id: 5, completed: false
          },{
            text: 'poiu', id: 5, completed: false
          },{
            text: 'qwer', id: 5, completed: false
          },
        ],
        newText: '',
        totalTodo: 0,
        visibility: 'all'
      }
    },
    // mounted() {
    //   this.todos =
    //     JSON.parse(localStorage.getItem('localTodo'))
    // },

    methods: {
      addTodo() {
        localStorage.setItem('localTodo', JSON.stringify(this.todos))

        this.todos.push({
          text: this.newText,
          completed: false,
          id: 5
        })
      },
      removeTodo(i) {
        this.todos.splice(i, 1)
      },
      selectAll() {
        this.todos.forEach((todo) => {
          todo.completed = !todo.completed
        });
      },
      todosData(value) {
        switch (value) {
          case 2:
            //alert(2)
            this.todos = this.todos.filter(todo => todo.completed === false)
            //  console.log(this.todos.filter(todo => todo.completed === false))
            break;
          case 3:
            // alert(3)
            // console.log(this.todos.filter(todo => todo.completed === true))

            this.todos = this.todos.filter(todo => todo.completed === true)
            break;
          default:
            console.log(this.todos)
            return this.todos
        }
      },
    },
    computed: {
      remainingTodo() {
        let totalTodo = 0;
        this.todos.forEach((todo) => {
          let i = 1;
          if (todo.completed === false)
            totalTodo += i
        });
        return totalTodo
      },

      filteredTodos() {
        if (this.visibility === 'all') {
          return this.todos
        } else if (this.visibility === 'active') {
           this.todos = this.todos.filter(todo => todo.completed === false)

        } else {
           this.todos = this.todos.filter(todo => todo.completed === true)

        }
      }
    },
    //watch: {
    //   'todos': function () {
    //     console.log(this.todos)
    //   }
    // }
  }
</script>

<style scoped>
</style>
