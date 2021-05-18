<template>
  <div class="row">
    <h1 v-once>{{ introduction }}</h1>
    <input @keyup.enter="submit" v-model="inputEmail" ref="emailInput" placeholder="Enter an E-Mail">
    <button @click="$emit('add-email', inputEmail); clearInput" ref="addButton" v-if="add">Add E-Mail</button>
    <button @click="$emit('remove-email', inputEmail); clearInput" ref="removeButton" v-if="remove">Remove E-Mail</button>
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
  methods: {
    submit: function() {
      if(this.add) this.$refs.addButton.click();
      else this.$refs.removeButton.click();
      this.clearInput();
    },
    clearInput: function() {
      console.log("Clearing");
      this.inputEmail = "";
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