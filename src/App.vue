<template>
  <v-app>
    <v-main>
      <SignUP></SignUP>
    </v-main>
  </v-app>
</template>

<script>
import SignUP from "./components/SignUp.vue"

export default {
  name: 'App',

  components: {
    SignUP
  },

  data: () => ({
    //
  }),
}
</script>
<style>
#app{
  font-family:Avenir,Arial, Helvetica, sans-serif;
  -webkit-font-smoothing:antialiased ;
  -moz-osx-font-smoothing:grayscale;
  text-align: center;
  columns: #2c3e50;
  margin-top: 60px;
}

</style>
