<template>
    <div class="inputbox shadow">
       
        <input type="text" v-model="newTodoItem" placeholder="입력해주세요.">
        <button v-on:click="addTodo">+</button>
    </div>
</template>

<script>
export default {
    data(){
        return {
            newTodoItem:''
        }
    },
    methods: {
        addTodo() {
           // console.log(this.newTodoItem);

              //inputbox 빈값인지 확인
            if( this.newTodoItem !== "") {
                var value = this.newTodoItem && this.newTodoItem.trim(); //?
                localStorage.setItem(value, value);
                this.clearInput();
            }
        },
        clearInput(){
            this.newTodoItem='';
        }
    }
}
</script>

<style scope>
input:focus {
    outline:none;
}
.inputbox {
    background: #fff;
    height:50px;
    border-radius:5px;
    line-height: 50px;
}
.inputbox input{ 
    border-style: none;
    font-size:.9rem;
}
button{
    float: right;
    background: linear-gradient(90deg,#6478fb,#8763fb);
    display: inline-block;
    width: 3rem;
    border:none;
    border-radius: 0 5px 5px 0;
    color:#fff;
    font-size:20px;
    font-weight:900;
}
</style>