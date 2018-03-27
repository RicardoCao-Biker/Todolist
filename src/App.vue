<template>
  <div>
    <h1>{{title}}</h1>
    <div class="inputing"><input type="text" v-model="noteinfo">
    <button @click="memory(item)">记录</button>
    </div>
    <ul>
      <li v-for="item in items" @click='togglestatus(item)' :class='{isdone:item.done}' ><input type="checkbox" id="check">{{item.label}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data:function(){
    return{
    title : '我的备忘录',
    items : [],
    }
  },
  methods:{
      memory:function (item) {
        this.items.push({
          label:this.noteinfo,
          done:false
        }),
        this.noteinfo=''
      },
      togglestatus:function (item){
        item.done = !item.done
      }
  }
}
</script>

<style>
.isdone{
  text-decoration:line-through
}
.inputing{
  width:35%;
  margin: 0 auto;
}
#check{
  width:20px;
  height:20px;
  vertical-align:middle;
}
input{
  width:80%;
  height:30px;
  border-radius: 5px;
  display: inline-block;
  margin:0 auto;
}
button{
  height:35px;
  width:18%;
  border-radius: 5px;
}
h1{
  text-align: center;
  margin-top:60px;
  margin-bottom: 60px;
}
ul{
  width:20%;
  margin:40px auto 40px auto;
  list-style:none; 
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;

}
</style>
