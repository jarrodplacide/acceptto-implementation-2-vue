<template>
  <div class="row mt-3">
    <h3 v-once class="mb-4">{{ introduction }}</h3>
    <div class="form-group">
      <input class="form-control" @keyup.enter="submit" v-model="inputEmail" ref="emailInput" placeholder="Enter an E-Mail">
    </div>
    <div class="d-grid mt-2">
      <button type="button" class="btn btn-primary"
              @click="$emit('add-email', inputEmail); clearInput" ref="addButton" v-if="add">Add E-Mail</button>
      <button type="button" class="btn btn-danger"
              @click="$emit('remove-email', inputEmail); clearInput" ref="removeButton" v-if="remove">Remove E-Mail</button>
    </div>
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
      return !this.emails.includes(this.inputEmail) && this.inputEmail.length > 0;
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