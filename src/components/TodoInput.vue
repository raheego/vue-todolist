<template>
    <div class="inputBox shadow">
        <input type="text" v-model="newTodoItem" placeholder="입력해주세요." v-on:keyup.enter="addTodo">
        <button v-on:click="addTodo" class="bt_add">+</button>
    </div>
</template>

<script>
export default {
   data(){
        return {
            newTodoItem: ''
        }
    },
    methods: {
        addTodo(){
            //inputbox 빈값인지 체크, 빈값이 아니면 로직 수행
            if(this.newTodoItem !== ''){
                var value = this.newTodoItem && this.newTodoItem.trim();
                //localStorage.setItem(value, value);
                //App컴포넌트로 이벤트 전달
                this.$emit('addTodo', value);
                this.clearInputbox();
            }
        },
        clearInputbox(){
            this.newTodoItem = '';
        }
    }
}
</script>

<style scope>

</style>