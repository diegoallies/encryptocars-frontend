<template>
    <div class="bg-dark bloc aqua-border">

      <div class="row bhd">
    <div class="col bhd">
      <h2 class="hed bg-dark bhd">{{ post.fullname }}</h2> <br>
        <h5 class="txt bg-dark bhd">{{ post.title }}</h5>
        <br>
    </div>
    <div class="col bhd">
     <h2 class="bhd">R {{ post.price }}
       </h2> 
       <br>
       <h6 class="bhd">
         category: {{ post.category }}
       </h6>
    </div>
    </div>
        

        <router-link :to="{name:'SinglePost', params: {id: post._id}}">
        <div class="p-image"><img :src="post.img" alt="Open image to alter content"/></div>
        </router-link>
 
    </div>

</template>

<script>
export default {

    props: ["post"],

    methods:{
    
    

  }
  ,
  name: 'Profile',
  computed: {
    currentUser() {
      return this.$store.state.auth.user;
    }
    
  },

}
</script>

<style>
.p-image {
  object-fit: contain;
  overflow: hidden;

}

.p-image img {
  width: 100%;
}

.bhd {
  background: rgb(35, 63, 63) !important;
  margin: 0%;
  overflow: hidden;
}
.hed, .txt {
  margin-left: 2%;
  margin-top: -1%;
  border-radius: 10%;
  background: rgb(35, 63, 63) !important;
}

.txt {
    margin-bottom: -1%;
}

.aqua-border {
  border: #00ffd5 0.5px solid;
  border-radius: 1.5%;
}

.bloc {
  width: 100%;
  padding-top: 1%;
  padding-bottom: 1%;
  border-radius: 1.5%;
  color: aqua;
  margin-top: 2%;
  margin-left: -2%;
  background: rgb(35, 63, 63) !important;

}

@media screen and (max-width:700px) { 

.hed {
  font-size: 180%;
  margin-top: 0%;
}


}
</style>