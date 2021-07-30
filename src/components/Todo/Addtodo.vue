<template>
    <form @submit.prevent="submit">
        
        <input type="text" placeholder="Add todo" v-model="title">
        <input type="submit" value="Add">
    </form>
</template>
<script>
// import uuid from "uuid"

export default {
    name:"Addtodo",
    data(){
        return {
            title:''
        }
    },
    methods:{
        submit(){
            const todo={
                id:Date.parse(new Date()),
                title:this.title,
                completed:false
            };
            this.title="";
            this.$emit("add-todo",todo);
        }
        
    }
}
</script>
<style>
form{
    display: flex;

}
input[type="text"]{
    flex:10;
    border:1px solid #ccc;
    padding: 4px;
}
input[type="submit"]{
    flex: 2;
    border:1px solid #ccc;
}
</style>