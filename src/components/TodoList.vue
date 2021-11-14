<template>
    <section>
        <article>
            <div class="arti-wrap">
                <ul class="todo-list">
                    <li v-for="(todoItem, index) in propsdata" v-bind:key="todoItem">
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
    props:['propsdata'],
    data(){
        return {
            todoItems: []
        }
    },
    methods: {
        removeTodo(todoItem, index){
            this.$emit('removeTodo', todoItem, index);
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