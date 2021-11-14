<template>
    <section>
        <article>
            <div class="arti-wrap">
                <ul class="todo-list">
                    <li v-for="(todoItem, index) in todoItems" v-bind:key="todoItem">
                        <i class="checkBtn fas fa-check" aria-hidden="true"></i>
                        {{ todoItem }}
                        <span class="removeBtn" type="button" v-on:click="removeTodo(todoItem, index)">
                            <i class="far fa-trash-alt" aria-hidden="true"></i>
                        </span>
                    </li>
                </ul>
            </div>
        </article>  
    </section>
</template>

<script>
export default {
    data(){
        return {
            todoItems: []
        }
    },
    created(){
        if(localStorage.length > 0){
            for(var i=0; i<localStorage.length; i++){
                this.todoItems.push(localStorage.key(i))
            }
        }
    },
    methods: {
        removeTodo(todoItem, index){
            localStorage.removeItem(todoItem);
            this.todoItems.splice(index,1);
        }
    }
}
</script>

<style scoped>
.todo-list {
    width: 100%;
}
.todo-list li {
    display:  flex;
    min-height: 50px;
    line-height: 50px;
    margin: 0.5rem 0;
    border-bottom: 1px dashed #aeaeae;
}
.checkBtn {
    line-height: 45px;
    color: #62acde;
    margin: 0 1rem;

}
.removeBtn {
    margin-left: auto;
    color:#de4343;
}
</style>