<template></template>
<script>
import Vue from "vue";
export default Vue.extend({
  async asyncData(context) {
    const headers = {};
    
    const data = {
      guild: await new Promise((resolve, reject) =>
        context
          .$axios({
            method: "GET",
            headers: headers,
            url: `/api/v1/servers/${context.route.params.code}`,
            timeout: 3000,
          })
          .then((response) => {
            context.redirect(
              `https://www.masuru.in.th/servers/${context.route.params.code}`
            );
          })
          .catch((error) =>
            context.redirect(`https://www.masuru.in.th/servers/lilia-support`)
          )
      ),
    };
    return data;
  },
});
</script>
