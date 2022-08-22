<template>
  <div>
    <paginate :page="page" :length="10" @updatePage="goServer" />
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
  },

  methods: {
    goServer(data) {
      alert(data)
    }
  }
};
</script>