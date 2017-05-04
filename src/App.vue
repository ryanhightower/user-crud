<template>
  <div id="app">
    <button type="button" name="button" @click="getUsers">Get Users</button>
    <button type="button" name="button" @click="addUser">Add User</button>
    <user-display :users='users'></user-display>
  </div>
</template>

<script>
import Axios from 'axios'
import UserDisplay from './components/UserDisplay'

export default {
  name: 'app',
  data () {
    return {
      users: {},
      show: {
        addForm: false,
        updateForm: false
      }
    }
  },
  components: {
    UserDisplay
  },
  methods: {
    getUsers () {
      Axios.get('//yoursco-web-api.herokuapp.com/users').then((res) => {
        console.log(res.data)
        this.users = res.data
      })
    },
    addUser () {
      Axios.get('//yoursco-web-api.herokuapp.com/users').then((res) => {
        console.log(res.data)
        this.users = res.data
      })
    },
    updateUser () {
      Axios.get('//yoursco-web-api.herokuapp.com/users').then((res) => {
        console.log(res.data)
        this.users = res.data
      })
    },
    deleteUser () {
      Axios.get('//yoursco-web-api.herokuapp.com/users').then((res) => {
        console.log(res.data)
        this.users = res.data
      })
    }
  }
}
</script>

<style>

</style>
