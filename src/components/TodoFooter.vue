<template>
    <div>
        <button type="button" v-on:click="clearTodo">전체삭제</button>
    </div>
</template>

<script>
export default {
    /*
    methods: {
        clearTodo(){
            localStorage.clear();
        }
    }
    */
    methods: {
        clearTodo(){
            this.$emit('removeAll');
            // 하위->상위 이벤트 발생 
        }    
    }
}
</script>