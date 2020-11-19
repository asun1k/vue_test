<template>

  <div>
    <img  width="350"  alt="Swed logo" src="https://i2.wp.com/insurance-edge.net/wp-content/uploads/2019/10/swedbank-partner-with-munich-re.jpg?fit=693%2C385&ssl=1&w=640">

    <p>
      <input v-model="user.email" placeholder="email">
    </p>
    <p>
      <input v-model="user.name" placeholder="name">
    </p>
    <p>
      <input v-model="user.age" type="number" placeholder="age">
    </p>
    <button v-on:click="register()">Register</button>
    {{ message }}
    <br><br><br><br><br>
    <table border style="border: black" width="500" align="center">
      <tr bgcolor="#add8e6">
        <th>Name</th>
        <th>Email</th>
        <th>Age</th>
      </tr>
      <tr v-for="row in resultList">
        <th>{{ row.name }}</th>
        <th>{{row.email}}</th>
        <th>{{row.age}}</th>
      </tr>
    </table>
  </div>
</template>
<script>

let showResponse = function (response) {
  this.resultList = response.data;
}

let registerFunction = function () {
  let url = "http://localhost:8080/register";
  this.$http.post(url, this.user)
      .then(this.showResponse)
  this.user.email = ""
  this.user.name = ""
  this.user.age = ""
}

export default {
  methods: {
    register: registerFunction,
    showResponse: showResponse
  },
  data: function () {
    return {
      user: {},
      resultList: []
    }
  }
}
</script>

