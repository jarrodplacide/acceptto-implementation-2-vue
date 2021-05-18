<template>
  <div class="row">
    <h1 v-once>{{ introduction }}</h1>
    <input v-model="newEmail" placeholder="Enter an E-Mail">
    <button @click="$emit('add-email', newEmail)">Add E-Mail</button>
  </div>
</template>

<script>
export default {
  name: "EmailInput",
  props: {
    introduction: String
  },
  data() {
    return {
      newEmail: ""
    }
  }
}
</script>

<style scoped>

</style>