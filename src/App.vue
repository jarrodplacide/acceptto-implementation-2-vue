<template>
  <div id="app">
    <h1 class="app__title">Acceptto Assessment: Implementation 2</h1>
    <div class="container w-75">
      <EmailInput
          introduction="Enter a new e-mail below to add or an existing e-mail to remove"
          v-bind:emails="emails"
          @add-email="addEmail"
          @remove-email="removeEmail"
      />
      <EmailList v-bind:emails="emails"/>
    </div>
  </div>
</template>

<script>

import EmailInput from './components/EmailInput.vue'
import EmailList from "./components/EmailList.vue";


export default {
  name: 'App',
  components: {
    EmailInput,
    EmailList
  },
  data() {
    return {
      emails: []
    }
  },
  methods: {
    addEmail: function(newEmail) {
      this.emails.push(newEmail);
    },
    removeEmail: function(existingEmail) {
      this.emails = this.emails.filter( value => value !== existingEmail)
    }
  }
}
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1.app__title {
  font-weight: 800;
  text-transform: uppercase;
  margin-bottom: 25px
}
</style>
