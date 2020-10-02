
<template>
    <div class="inputBox shadow">
        <input type="text" v-model="newTodoItem" placeholder="입력해주세요." v-on:keypress.enter="addTodo">
        <button v-on:click="addTodo">+</button>
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
                localStorage.setItem(value, value);
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
input:focus {
  outline: none;
}
.inputBox {
  background: white;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}
.inputBox input {
  border-style: none;
  font-size: 0.9rem;
}
button {
    float:right;
    height:100%;
    background: linear-gradient(90deg,#6478fb,#8763fb);
    display: inline-block;
    width: 3rem;
    border-radius: 0 5px 5px 0;
    border:0;
    color:#fff;
    font-weight:900;
    font-size:20px;
}
</style>