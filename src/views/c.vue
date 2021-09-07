<template>
  <v-card
    max-width="100%"
   
  >
    <v-img
      class="img"
      src="https://images.unsplash.com/photo-1625472603525-6b77bfed6165?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1550&q=80"
      height="100%"
      dark
      @click="get()"
    >

      <v-row >
        <v-card-title>
          <v-btn
            dark
            icon
          >
            <v-icon>mdi-chevron-left</v-icon>
          </v-btn>

          <v-spacer></v-spacer>

          <v-btn
            dark
            icon
            class="mr-4"
          >
            <v-icon>mdi-pencil</v-icon>
          </v-btn>
 
          <v-btn
            dark
            icon
            @click="visible=1"
          >
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </v-card-title>

        <v-spacer></v-spacer>

        <v-card-title >
          <h1 class="t">
            Kanga Lock
          </h1>
        </v-card-title>
      </v-row>
    </v-img>
    <v-img v-if="visible==1"
        src="../assets/Insta_logo.png"
        height="25%"
        width="25%"
        @click="visible=0"
    ></v-img>
    <v-list two-line>
      <v-list-item>
        <v-list-item-icon>
          <v-icon color="indigo">
            mdi-phone
          </v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>(010) 2935-9685</v-list-item-title>
          <v-list-item-subtitle>Mobile</v-list-item-subtitle>
        </v-list-item-content>

        <v-list-item-icon>
          <v-icon @click="visible=1">mdi-message-text</v-icon>
        </v-list-item-icon>
      </v-list-item>

      <v-list-item>
        <v-list-item-action></v-list-item-action>

        <v-list-item-content>
          <v-list-item-title> - </v-list-item-title>
          <v-list-item-subtitle>Work</v-list-item-subtitle>
        </v-list-item-content>

        <v-list-item-icon>
          <v-icon @click="say('문자를 보내시겠습니까?')">mdi-message-text</v-icon>
        </v-list-item-icon>
      </v-list-item>

      <v-divider inset></v-divider>

      <v-list-item>
        <v-list-item-icon>
          <v-icon color="indigo"
          >
            mdi-email
          </v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>i663566@naver.com</v-list-item-title>
          <v-list-item-subtitle>Personal</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-list-item>
        <v-list-item-action></v-list-item-action>

        <v-list-item-content>
          <v-list-item-title>chs29359685@gmail.com</v-list-item-title>
          <v-list-item-subtitle>Work</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider inset></v-divider>

      <v-list-item>
        <v-list-item-icon>
          <v-icon color="indigo">
            mdi-map-marker
          </v-icon>
        </v-list-item-icon>

        <v-list-item-content>
          <v-list-item-title>Daehak-ro 99</v-list-item-title>
          <v-list-item-subtitle>Daejeon, Tips Town</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </v-card>
  
</template>

<script>
import axios from 'axios'
export default {
  name: "c",

  data: () => ({
    visible:0,
      menu:[{
        "title": "A"
      },{
        "title": "B"
      },{
        "title": "C"
      }
      ],

  }),
  methods:{
    say:function(msg){
      confirm(msg)
    },
    get:function(){
      axios.post('http://localhost:3000/posts' , {name:"new"}).then(
        res=>{
          console.log(res);
        }
      )
    }
  }
};
</script>
<style>
.t{
  position:absolute;
  top:50%;
  left:50%;
  width:500px;
  font-size: 75px;
  margin-left: -250px;
}
.img{
  text-align: center;
}
</style>

