<template>
  <div class="home">
    <IssueList :list="list" />
  </div>
</template>

<script>
import IssueList from "@/components/IssueList.vue";

export default {
  name: "Home",
  components: {
    IssueList,
  },
  data() {
    return {
      list: [],
    };
  },
  methods: {
    getList() {
      this.$axios
        .get("https://api.github.com/repos/facebook/create-react-app/issues")
        .then((res) => {
          console.log(res);
          this.list = res.data;
        })
        .catch((e) => {
          console.log(e);
        });
    },
  },
  mounted() {
    this.getList();
  },
};
</script>
