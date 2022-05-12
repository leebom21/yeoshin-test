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
          this.list = res.data;
          this.commentsSort();
        })
        .catch((e) => {
          console.log(e);
        });
    },
    commentsSort() {
      this.list.sort(function (a, b) {
        return b.comments - a.comments;
      });
    },
  },
  mounted() {
    this.getList();
  },
};
</script>
