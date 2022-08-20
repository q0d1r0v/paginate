<template>
  <div>
    <paginate :page="1" :length="27" :total-visible="6" />
  </div>
</template>
<script>
import paginate from "../components/paginate.vue";
export default {
  name: "home-page",
  components: { paginate },
};
</script>
