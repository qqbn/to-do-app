<template>
     <div class="list">
                <div class="divtasks">
                        <h3>Lets add sth to your list!</h3>
                        <div class="contextTasks">
                            <div class="paragraph" >
                                <div class="box" v-for="(taskText,n) in tasks" v-bind:key="taskText.id">
                                    <p class="task">{{ tasks[n].taskText }}</p>
                                    <p class="date">{{ tasks[n].date }}</p>
                                    <img @click="removeTasks(n)" class="deletepng" src="../assets/thrash.png" alt="thrash">
                                    <img src="../assets/edit.png" class="edit" @click="idReturn(tasks[n].id)" >
                                </div>

                            </div>
                        </div>
                </div>
            </div>
</template>
<script>
export default {
    name:'List',
    props:['tasks'],
    data (){
        return{
        }
    },
    methods:{
        removeTasks(n){
            confirm('Are u sure?');
            this.tasks.splice(n,1);
            this.saveTasks();
        },
        saveTasks(){
            const parsed = JSON.stringify(this.tasks);
            localStorage.setItem('tasks', parsed);
        },
        idReturn(id){
            this.$emit('id-emit', id);
        }
    }
}
</script>