<template>
  <div>
    <paginate :page="1" :length="4" :total-visible="6" />
  </div>
</template>
<script>
import paginate from "../components/paginate.vue";
export default {
  name: "home-page",
  components: { paginate },
};
</script>
