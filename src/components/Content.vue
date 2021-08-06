<template>
    <div class="content">
        <List v-bind:tasks="tasks" v-on:id-emit="setId($event)"/>
        <Form v-on:edited-tasks="fillArray($event)" :id="id" :newTasks="tasks"/>
    </div>
</template>
<script>
import List from './List.vue'
import Form from './Form.vue'
export default {
   name: 'Content',
   data(){
       return{
           tasks: [ ],
           id: null,
       }
   },
   components:{
       Form,
       List,
   },
   mounted(){
        if(localStorage.getItem('tasks')){
            this.tasks=JSON.parse(localStorage.getItem('tasks'));
        }
    },
   methods: {
       fillArray(test){
          this.tasks=test;
       },
       setId(test2){
           this.id=test2;
       }
   }
}
</script>