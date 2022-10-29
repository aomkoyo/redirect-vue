<template></template>
<script>
import Vue from "vue";

export default Vue.extend({
  async asyncData(context) {
    context.redirect(`https://www.masuru.in.th/discovery/pages/1`);
  },
});
</script>
