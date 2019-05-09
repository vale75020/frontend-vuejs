<template>
  <div class="home">

    <!-- {{ users }} pour afficher les users recuperés avec fetch -->
    <div v-for="(user, index) in users" :key="index"> <!--boucle for pour créer des div avec chaque user. index est passé pour avoir une clé unique-->
       <User :info="user"/> <!-- component User importé :
    <div>
     <div class="identity">{{user.firstname}} {{user.lastname}}</div>
     <div class="city">City: {{user.address.city}}</div>
     <div class="username">Email: {{user.username}}</div>
     <hr>
    </div> -->
      <hr>
    </div>
  </div>
</template>

<style lang="scss"> // ajouter lang="scss" pour utiliser sass
.home {
  .identity{
    font-size: 20px;
    font-weight: bold;
    color: #333;
  }
  .username {
    color: darkgreen;
    font-size: 12px;
  }
}
</style>

<script>
// @ is an alias to /src
import axios from 'axios'; // import d'axios
import User from '../components/User.vue';

export default {
  name: 'home',
  data() {
    return{
      users: "", //comme un state on va le riemplir avec response.data
    }
  },
  components: { // à declarer pour injecter les datas
      User // je dis à mon component Home qu'il peut utiliser User
  },
  beforeCreate() { //beforeCreate pour faire un preload des données
    axios.get('http://localhost:3000/users')
    .then((response) => {
      console.log('response: ', response);
      this.users = response.data  // données recuperés avec le fetch (all users)
    })
    .catch((error) => {
      console.log('error: ', error);
    });
  }
}
</script>
