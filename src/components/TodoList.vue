<template>
<section>
    <ul>
        <li v-for="todoItem in todoItems">{{ todoItem }}</li>
    </ul>
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
            for(var i = 0; i < localStorage.length; i++){
                this.todoItems.push(localStorage.key(i));
            }
        }
    }
}
</script>

<style scope>
ul{
    list-style:none;
    padding-left:0;
    margin-top:0;
    text-align:left;
}
li {
    display:flex;
    min-height:50px;
    height:50px;
    line-height:50px;
    margin:.5rem 0;
    padding: 0 .9rem;
    background:#fff;
    border-radius:5px;
}

</style>