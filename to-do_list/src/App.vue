<script>
  export default{
    data(){
      return{
        list:[],
        item:''
      }
    },
    methods:{
      add_list(){
        this.list.push(this.item);
        console.log(this.list);
      },
      deleteItem(index){
        this.list.splice(index,1)
      },
      sort(){
        this.list.sort()
      }
    }
  }
</script>

<template>
  <div class="wrapper">
    <h1>Список дел</h1>
    <p>Список дел — это всего лишь перечисление того, чем вам нужно заняться. В таком списке может быть всё, что угодно. Но сам факт того, что вы записали дела, ещё не означает, что этот список будет по-настоящему полезным. Отслеживайте свои дела и убирайте выполненные. Приступим:</p>
    <input type="text" v-model="item">
    <button @click="add_list()" v-if="item==''">Добавить</button>
    <button @click="add_list()" v-else>Добавить</button>
    <hr>
    <button @click="sort()">Сортировка</button>
    <ul>
      <li v-for="(text_item, index) in list">{{ text_item }}<span @click="deleteItem(index)"> &#10004;</span></li>
    </ul>
  </div>
</template>

<style scoped>
.wrapper{
    width: 800px;
    margin: auto;
    margin-top: 100px;
    background-color: rgb(71, 125, 141);
    border-radius: 15px;
    text-align: center;
    color: fff;
    font-family: Arial, Helvetica, sans-serif;
    padding: 20px;
}
.wrapper h1{
    margin-top: 10px;
}
.wrapper p{
    text-align: justify;
    color: #fff;
}
.wrapper ul{
    list-style: none;
    text-align: left;
}
.wrapper li{
    margin: 10px;
}
.wrapper input{
    width: 80%;
    line-height: 30px;
    font-size: 20px;
    color: #625f5f;
    text-align: right;
    border-radius: 10px;
}
.wrapper button{
    margin-left: 5px;
    line-height: 30px;
    font-size: 20px;
    color: #625f5f;
    text-transform: uppercase;
    border-radius: 10px;
}
.wrapper hr{
    background-color: #fff;
    margin-top: 15px;
    margin-bottom: 15px;
}
.wrapper span{
    color: rgb(255, 0, 140);
    font-weight: 900;
}
.wrapper span:hover{
    font-size: 30px;
}
</style>