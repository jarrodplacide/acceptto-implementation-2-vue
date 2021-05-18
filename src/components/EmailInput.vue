<template>
  <div class="row">
    <h1 v-once>{{ introduction }}</h1>
    <input v-model="inputEmail" placeholder="Enter an E-Mail">
    <button @click="$emit('add-email', inputEmail)" v-if="add">Add E-Mail</button>
    <button @click="$emit('remove-email', inputEmail)" v-if="remove">Remove E-Mail</button>
  </div>
</template>

<script>
export default {
  name: "EmailInput",
  props: {
    introduction: String,
    emails: Array
  },
  computed: {
    add: function() {
      return !this.emails.includes(this.inputEmail)
    },
    remove: function() {
      return this.emails.includes(this.inputEmail)
    }
  },
  data() {
    return {
      inputEmail: ""
    }
  }
}
</script>

<style scoped>

</style>