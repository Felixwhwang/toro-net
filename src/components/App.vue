<template >
  <div id="app" >
    <div id="menu">
       <br>

        <div class="container ">
            <div v-if="!this.$store.state.user.displayName">
            <router-link to="/">Home</router-link>
          <!--<a v-if="!this.$store.state.user.displayName" href="/register" @click="register">Register</a>-->
            <router-link to="/register">Register</router-link>
            <router-link to="/login">Login</router-link>
      <!-- Insert cool photo -->
          </div>
        </div>
    </div>
    <h1><a href="/login" style="text-decoration:none;"> {{ title }}</a></h1>
    <img src="https://user-images.githubusercontent.com/31264160/31743405-e7d712cc-b40f-11e7-8c22-d7d9b7b54c43.png">
          <div class="row" v-if="this.$store.state.user.displayName">
          <a href="/logout" @click="logout">Logout</a>
          <br>
        </div>

          <router-view />

      <div class="">
        <br>
        <br>
        <br>
        <br>
      </div>



  </div>

</template>

<script>
export default {
  name: 'app',
  // data:
  // {
  //   showContent:true,
  // },
  data () {
    return {
      title: 'Toro-Net',

    }
  },
  methods: {
    logout() {
      this.$store.dispatch('logout')
    },
    hpStaus(){
      // showNav=false;
      console.log(this.$store);

    },
  },
  mounted() {
    this.$store.dispatch('getUser')
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000;
}

#menu {
  background-image: linear-gradient(to bottom ,#3498db 0,#fff);
  padding: 30px
}

#menu a {
  font-size: 30px;
  text-decoration: none;
  padding-top: 20px;
  color: #000;
  margin-left: 20px;
}

#menu a:hover {
  color: #204d74;
}

h1, h2 {
  font-weight: normal;
}

h1 {
  color: #645f72;
  font-style: italic;
  font-size: 55px;
  font-family: comic sans ms;
  background: linear-gradient(180deg,#268dd8, #c4d0da);
      background-clip: border-box;
  -webkit-background-clip: text;
  -webkit-text-fill-color: #0000;
}

ul {
  list-style-type: none;
  padding: 0;
}

a {
  color: #860038;
}

.row {
    display: -ms-flexbox;
    display: flex;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
    margin-left: 70px;
}
</style>
