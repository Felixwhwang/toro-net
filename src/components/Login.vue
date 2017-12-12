<template>
  <div class="container col-sm-4 align-items-center">

    <!-- navbar loaded -->
      <nav-bar> </nav-bar>

        <form action="/auth/local" method="post">
                      <div class="">
                         <h2>Log In!</h2>
                      </div>
                  <hr>
                  <br>
                      <div class="form-group row">
                          <input class="form-control col-sm-10" type="email" name="email" placeholder="Email" v-model="email">
                      </div>

                      <div class="form-group row">
                          <input type="password" class="form-control col-sm-10" id="password" name="password" placeholder="Password" v-model="password">
                      </div>
                      <button class="btn btn-success btn-lg" @click="login" type="submit">Login</button>
                      <a href="/auth/github" class="btn btn-github btn-sm"><i class="fa fa-github"></i> Login with Github</a>
        </form>



  </div>
</template>

<style scoped>
.btn-github {
  border: 0;
  background: #444;
  color: white;
}
.btn-github:hover {
  background: #2B2B2B;
  color: white;
}

.btn-google {
  border: 0;
  background: #db4437;
  color: white;
}

.btn-google:hover {
  background: #c90b0b;
  color: white;
}

.form-group input {
  margin-top: 10px;
  width: 30%;
  display: inline-block;
  box-shadow: 10px 10px 10px -10px rgba(11,90,110,1);
}
.btn-group-sm > .btn, .btn-sm {
    padding: 16px;
    font-size: .875rem;
    line-height: 1.5;
    border-radius: .2rem;
}

.btn-group-lg > .btn, .btn-lg {
    padding: 10px;
    font-size: 1.25rem;
    line-height: 1.5;
    border-radius: .3rem;
}

.row {
    display: -ms-flexbox;
    display: flex;
    -ms-flex-wrap: wrap;
    flex-wrap: wrap;
    margin-left: 70px;
}
</style>

<script>
export default {
  name: 'Login',
  data() {
    return {
      email: '',
      password: ''
    };
  },
  methods: {
    login() {
      const user = {
        email: this.email,
        password: this.password
      }
      this.$store.dispatch('login', user)
    }
  }
}
</script>
