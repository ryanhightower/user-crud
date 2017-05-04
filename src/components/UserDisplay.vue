<template>
<div>
  <table>
    <tr v-for="user in users">
      <td>{{user.id}}</td>
      <td>{{user.email}}</td>
    </tr>
  </table>
  <pre>{{users}}</pre>
</div>
</template>

<script>
import Axios from 'axios'

export default {
  props: ['users'],
  data () {
    return {}
  },
  mounted () {
    // This lifecycle hook could be used to mount users on load.
    // Axios.get('//yoursco-web-api.herokuapp.com/users').then((res) => {
    //   console.log(res.data)
    //   this.users = res.data
    // })
  },
  methods: {
    getUsers () {
      Axios.get('//yoursco-web-api.herokuapp.com/users').then((res) => {
        console.log(res.data)
        this.users = res.data
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
