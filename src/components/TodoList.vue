<template>
    <section>
        <ul>
            <li v-for="(todoItem, index) in propsdata" :key="todoItem">
                {{ todoItem }}
                <button type="button" v-on:click="removeTodo(todoItem, index)" class="bt_delelte">삭제</button>
            </li>
        </ul>
    </section>
</template>

<script>
export default {
      /*
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
    },
    */
    //props속성 추가
    props: ['propsdata'],
    methods: {
    	removeTodo(todoItem, index){
            this.$emit('removeTodo', todoItem, index);
        }
    }    
}
</script>