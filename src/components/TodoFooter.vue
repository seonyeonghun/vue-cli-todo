<template>
    <footer>
        <div class="footer-wrap">
            <span class="clearAllBtn" v-on:click="clearTodo">모두 삭제</span>
        </div>
    </footer>
</template>

<script>
export default {
    methods: {
        clearTodo(){
            this.$emit('removeAll');
        }
    }
}
</script>

<style scoped>
.footer-wrap {
    text-align: center;
}
.clearAllBtn {
    color: #e20303;
    border: 1px solid #e20303;
    padding:.5rem 1rem;
    border-radius: 5px;
    cursor: pointer;
}
</style>