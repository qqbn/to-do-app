<template>
    <div id="app">
      <Header/>
      <Content/>
    </div>
</template>

<script>
import Header from'./components/Header.vue'
import Content from './components/Content.vue'

export default {
  name: 'App',
  components:{
    Header,
    Content,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,400;1,500&display=swap');
*{
    box-sizing: border-box;
    margin: none;
    padding: none;
}
#app{
    margin: 0;
    padding: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.header{
    height: 10vh;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
}

.header h1{
    font-family: 'Montserrat', sans-serif;
    font-size: 32px;
}
.header2{
    height: 60px;
    border-bottom: 5px solid #2fd1d4;
}
.content{
    margin: 0;
    width: 100%;
    height: 85vh;
    display: flex;
    justify-content: center;
    align-items: center;
}

.list{
    font-family: 'Montserrat', sans-serif;
    height: 100%;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.divtasks{
    width: 700px;
    height: 500px;
    border-radius: 5px;
    box-shadow: 1px 1px 5px #919999;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}
.paragraph{
    display: flex;
    justify-content: center;
    flex-direction: column;
    align-items: center;
    width: 100%;

}

.box{
   font-size: 22px;
   font-weight: 400;
   width: 100%;
   display: flex;
   justify-content: space-around;
   align-items: center;
}
.date{
    font-weight: 600;
    color: #2fd1d4;
}
.box p{
    font-size: 22px;
   font-weight: 400;
}
button{
    margin-right: 0;
}
.contextTasks{
    height: 100%;
    width: 100%;
}
h3{
    text-align: center;
    font-size: 30px;
    height: 40px;
}
.form{
    margin-top: 0;
    height: 200px;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-direction: column;
    font-family: 'Montserrat', sans-serif;
}

.header3{
    height: 50px;
    border-bottom: 5px solid #2fd1d4;
}
.input{
    margin-top: 0;
    width: 300px;
    height: 40px;
    font-size: 20px;
    border-radius: 5px;
    border: 2px solid #4d5454;
}

.btn{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100px;
    height: 50px;
    background-color: #2fd1d4;
    font-weight: 600;
    border-radius: 5px;
    cursor: pointer;
    border: none;
}

.btn:hover{
    background-color: #4d5454;
    color: #2fd1d4;

}


.deletepng{
    height: 20px;
    width: 20px;
    cursor: pointer;
}

.edit{
    height: 20px;
    width: 20px;
    cursor: pointer;
}
</style>
