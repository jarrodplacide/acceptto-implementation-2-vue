<template>
  <div class="email-container row mt-3" v-if="activeList">
    <h2>Submitted E-Mails:</h2>
    <ul class="email-list">
      {{emailDisplay}}
    </ul>
  </div>
</template>

<script>
export default {
  name: "EmailList",
  props: {
    emails: Array
  },
  computed: {
    activeList: function() {
      return this.emails.length
    },
    emailDisplay: function() {
      return this.emails.join(", ")
    }
  }
}
</script>

<style scoped>
.email-list {
  border: 1px solid grey;
  padding: 10px 0;
}
</style>