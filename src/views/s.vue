<template>
  <div class="s">
    <h1>My pick</h1>
    <v-row v-for="(img,i) in images" :key="i"
  
>  <v-col class="arrow" v-if="i == order"><v-icon @click="previous()">mdi-arrow-left-thick</v-icon></v-col>  
  <v-card 
    outlined
    max-height="30"
  >
  
    <v-img v-if="i == order"
      :src="img.link"
      
      width="500px"
      
      >

    </v-img>
    <v-btn v-if="i==order"
     @click="like()" 
    > <v-icon>mdi-cards-heart</v-icon></v-btn>
    <span v-if="i==order" > {{img.like}}</span>
  </v-card> 
      <v-col  class="arrow" v-if="i == order"><v-icon @click="next()">mdi-arrow-right-thick</v-icon></v-col>

    </v-row> 
  </div>

</template>

<script>
export default {
  name: "Home",
  data:()=>({
  images : [{"like":0,"link":"https://images.unsplash.com/photo-1625476255174-4db21bc943ea?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=934&q=80"},
            {"like":0,"link":"https://images.unsplash.com/photo-1625119161833-57f8a7009f7b?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=967&q=80"},
            {"like":0,"link":"https://images.unsplash.com/photo-1618274895748-18a83fd6e6a1?ixid=MnwxMjA3fDB8MHx0b3BpYy1mZWVkfDUzfFM0TUtMQXNCQjc0fHxlbnwwfHx8fA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=400&q=60"},
            {"like":0,"link":"https://images.unsplash.com/photo-1623777032143-86ab93b5eb92?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=904&q=80"},
            {"like":0,"link":"https://images.unsplash.com/photo-1610775302704-bd1e5b18f641?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=934&q=80"},
            {"like":0,"link":"https://images.unsplash.com/photo-1598309466969-494f63b2743c?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80"},
            {"like":0,"link":"https://images.unsplash.com/photo-1625571281329-9c10548b633b?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=934&q=80"},],
  
  order:0,
  }),
  methods:{
    next:function(){
      if ( this.order < this.images.length-1 ) this.order++;
      else this.order=0;
    },
    previous:function(){
      if ( this.order > 0 ) this.order--;
      else this.order=this.images.length-1;
    },
    like(){
      this.images[this.order].like++;
    }
    
  }
};
</script>

<style>
.arrow{
  margin-top: 50%;
  margin-bottom: 50%;
  text-align: center;
}
</style>