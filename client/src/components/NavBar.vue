<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-primary col-12 px-5">

    <a class="navbar-brand" href="#">
      Drink Store
    </a>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav ml-auto">
        <li class="nav-item">
          <a class="nav-link" v-if="isLoggedIn == true" @click="logout" href="#" style="color: white;">Logout</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  data () {
    return {
      isLoggedIn: false,
      token: localStorage.getItem('token')
    }
  },
  methods: {
    logout: function () {
      localStorage.clear()
      this.$router.push('/')
    }
  },
  created () {
    let token = localStorage.getItem('token')

    if (token) {
      this.isLoggedIn = true
    } else {
      this.isLoggedIn = false
    }
  }
}
</script>

<style>

</style>
