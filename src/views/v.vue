<template>
<div>
    <div class="app">
        <input class="id"  placeholder="who .. max 5 char" v-model="id" maxlength="5" >
        <input class="msg" placeholder="msg" v-model="msg" >
         <v-btn @click="push(id,msg)">push</v-btn>

    </div>
    
   
    <v-card max-height="1000px">

    </v-card>
</div>

</template>


<script>
import axios from "axios";

export default {
  name: "v",

  components: {
  },
  data: () => ({
    msg:'',
    id:'',

  }),  methods:{
        searchChangeFunc(event){
            this.msg = event.target.value
        },
        push: function(id,msg){
            var now = new Date();
            if(id == '') {alert('I need your ID ! '); return}
            if(msg == '') {alert('Just Say anything !'); return}
            axios.post('http://localhost:3000/posts' , {who:id,log:msg,time:now}).then(
                res=>{
                 console.log(res);
                }).catch(err=>{alert('Server is closed')})
        }

  }
};
</script>
<style scoped>
input{
    border: solid 1px black;
}
input .id{
    
}
div {
    background-color: aqua;
    padding: 20px;
    border: solid 2px black;
    
}
div .app {
    border:none;
    background-color: white;
}
</style>
