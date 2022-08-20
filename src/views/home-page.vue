<template>
  <div>
    <paginate :page="page" :length="8" :total-visible="6" />
  </div>
</template>
<script>
import paginate from "../components/paginate.vue";
export default {
  name: "home-page",
  components: { paginate },
  data() {
    return {
      page: 1
    }
  }
};
</script>
