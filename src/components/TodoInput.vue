<template>
    <section>
        <article>
            <div class="arti-wrap">
                <input type="text" v-model="todoInput">
                <button v-on:click="addTodo">추가</button>
            </div>
        </article>
    </section>
</template>

<script>
export default {
    data(){
        return {
            todoInput: ''
        }
    },
    methods: {
        addTodo() {
            if(this.todoInput != "") {
                var value = this.todoInput && this.todoInput.trim()
                localStorage.setItem(value, value);
                this.clearInput();
            }
        },
        clearInput() {
            this.todoInput = '';
        }
    }
}
</script>

<style scoped>
.arti-wrap {
    max-width: 74.375rem;
    margin: 50px auto;
    display: flex;
    justify-content: space-between;
}
input[type=text]{
    width:80%;
    outline: 0;
    border: 2px solid linear-gradient(90deg, dodgerblue, rgb(107, 20, 220));
}
button {
    width: 18%;
    height: 3rem;
}
</style>