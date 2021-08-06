<template>
    <div class="form">
                <div class="header3">
                    <h2>Lets add sth to your list</h2>
                </div>
                <input type="text" class="input" placeholder="Whats need to be done?" v-model="newTaskText">
                <input type="date" class="input" v-model="newDate">
                <button class="btn"  id="btn1" @click="add" v-if="!isEdit">Add!</button>
                <button class="btn" id="btn2" @click="save" v-if="isEdit">Edit!</button>
            </div>
</template>
<script>
export default {
    name: 'Form',
    props: ['id','newTasks'],
     data() {
            return {
            counter: 0,
            tasks: [ ],
            newTaskText: null,
            newDate: null,
            isEdit: false,
            taskId: null,
            }
    },
    watch: {
        id: function (newId) {
        console.log(newId);
        this.editTask(newId);
    },
        newTasks: function (newtasks){
            this.tasks=newtasks;
        }
    },
    methods: {
        add(){
            this.counter++
            this.tasks.push({
                id: Math.floor(Math.random() * 100000),
                taskText: this.newTaskText,
                date: this.newDate,
            })
            this.saveTasks();
            this.newTaskText='';
            this.newDate='';
        },
        saveTasks(){
            const parsed = JSON.stringify(this.tasks);
            localStorage.setItem('tasks', parsed);
        },
        editTask(n){
            this.isEdit=true;
            this.taskId=n;
            let wartosc;
            const tmp=JSON.parse(localStorage.getItem('tasks'));
            tmp.forEach((element)=>{
                if(element.id===n){
                    wartosc=element;
                }
            });
            this.newTaskText=wartosc.taskText;
            this.newDate=wartosc.date;
        },
        save(){
            const tmp=JSON.parse(localStorage.getItem('tasks'));
            tmp.forEach((element)=>{
                if(element.id===this.taskId){
                    element.taskText=this.newTaskText;
                    element.date=this.newDate;
                }
            });
            localStorage.setItem('tasks', JSON.stringify(tmp));
            this.tasks=tmp;
            this.isEdit=false;
            this.newTaskText='';
            this.newDate='';
            this.$emit('edited-tasks',this.tasks);
        },
    }
}
</script>