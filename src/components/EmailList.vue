<template>
  <div class="row">
    <h2>Submitted E-Mails:</h2>
    <ul class="email-list">
      <li v-for="email in emails" :key="email">
        {{email}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "EmailList",
  props: {
    emails: Array
  }
}
</script>

<style scoped>

</style>