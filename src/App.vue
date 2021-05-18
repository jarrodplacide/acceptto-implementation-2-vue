<template>
  <div id="app">
    <EmailInput
        introduction="Welcome. Please enter an e-mail below"
        v-bind:emails="emails"
        @add-email="addEmail"
        @remove-email="removeEmail"
    />
    <EmailList v-bind:emails="emails"/>
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
</style>
