<template>
  <div>
    <header>
     
     <h1> <center>Post: Actors </center></h1>
    </header>

    <main class="container">
      <router-view></router-view>
      
   <form>
    <div align="center" class="form-group">
      <label for="firstName">nombre</label>
        <input class="form-control input-sm" id="firstName" type="text" v-model="actor.firstName">
    </div>
   <div align="center" class="form-group">
    <label for="lastName">Apellido</label>
    <input class="form-control" id="lastName" type="text" v-model="actor.lastName">
  </div>
    
</form>

<form>
<div align="center">
  <button v-on:click.prevent="post">Guardar</button>
  </div>
 </form>

    </main>
    <footer>
      Footer
    </footer>
</div>
</template>

<script>
export default {
  data(){
    return{
      actor:{
        firstName:'',
        lastName:''
      }
    }
  },
  methods:{
    post:function(){
      this.$http.post('http://localhost:8081//sakila-spring-backend/actors',{
         firstName: this.actor.firstName,
         lastName: this.actor.lastName
      }).then(function(data){
        console.log(data);
      });
    }
  }
}
</script>



