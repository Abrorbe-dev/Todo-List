<template>
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">

    <div id="app" class="container mt-5">
        <div class="card p-5"
             style="background-color: lightblue;
      margin: auto; border-radius: 15px;">
            <h1 class="text-center mt-5">Todo List</h1>

            <!--Iput va Add-->
            <div class="d-flex mt-5 mb-5">
             <input 
                v-model="newTodo"
                class="form-control"
                placeholder="Yangi topshiriq qo'shing..."
                @keyup.enter="addTodo"
                />
                <!--Todo qo'shish-->
                <button 
                class="btn btn-success ms-2"
                :disabled="!newTodo.trim()"
                @click="addTodo">
                Add</button>
            </div>
            <h3 class="text-center mt-5">Tasks</h3>
            <!--List group-->
            <ul class="list-group ">
                <li class="d-flex align-items-center list-group-item justify-content-between mb-2 mt-2 form-control"
                    v-for="(todo, index) in todos "
                    :key="index"
                    style="background-color: aliceblue;"
                >
                    <span>{{ todo }}</span>
                    <button class="btn btn-danger ms-2"> <i class="fas fa-trash" @click="removeTodo(index)">Delete</i></button>

                </li>

            </ul>





        </div>
    </div>
</template>


<script>


export default{
  
    data() {
        return{
            newTodo: '',
            todos: []
        };
    },
    methods: {
        addTodo(){
            if (this.newTodo.trim())
                this.todos.unshift(this.newTodo)
            this.newTodo= '';
        },
        removeTodo(index){
            this.todos.splice(index, 1);
        },

    },
};

</script>

<style>
body{
    color: rgb(222, 236, 249);
}
#app{
    margin: auto;

}
.card{
    border-radius: 15px;
    color: lightblue;
}
button{
    color: white;
}
.list-group{
    background-color: rgb(173, 209, 237);
}
input{
    height: 40px;
    background-color:white;
}
</style>