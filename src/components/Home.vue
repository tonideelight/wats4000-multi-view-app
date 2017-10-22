<template>
  <div class="home">
    <div v-show="showForm" class="form-container">
      <h1>Join the Web Developers Club!</h1>
      <p>Sign up to access our special, secret page. Just create an account and answer a brief survey.</p>

      <p v-show="showError" class="error"> There are errors in the form, please check your information.</p>
      <form v-on:submit.prevent="validateForm">
        <p><label for="username">
        <input type="text" id="username" v-model="username" placeholder="Enter username">
        </label></p>
     
        <p><label for="email">
          <input type="email" id="email" v-model="email" placeholder="Enter email address">
          </label><p>
       
        <p><label for="password">
        <input type="password" id="password" v-model="password" placeholder="Enter password">
        </label><p>
    
        <p><label for="passwordVerify">
        <input type="password" id="passwordVerify" v-model="passwordVerify" placeholder="Enter password again">
        </label></p>
     

     

        <p><input type="submit" value="Submit"></p>
      </form>
    </div>
    <div v-show="!showForm" class="success-message">
      <h1>Thank you for signing up!</h1>
      <p>Please take our new member survey.<router-link to="Survey">Click here</router-link></p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      username: '',
      email: '',
      password: '',
      passwordVerify: '',
      showForm: true,
      showError: false
    }
  },
  methods: {
    validateForm: function () {
      // Validate the form by checking the following values:
      // username must not be blank
      // email must not be blank
      // password and passwordVerify must be equal
      //
      // When the form is validated, show the .success-message content
      // If the form is invalid, show the form error message
      if ((this.username != '') &&
      (this.email !='') &&
      (this.password === this.passwordVerify)){
        this.showForm = false;
      }else {

        this.showError =true;
      }
      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.error {
  border: 1px solid #aa0000;
  padding: 1rem;
  color: #aa0000;
}
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
