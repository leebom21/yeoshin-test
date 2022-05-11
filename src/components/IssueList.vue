<template>
  <div>
    <h2>게시판 리스트</h2>
    <ul v-for="item in list" :key="item.id">
      <li>
        이슈번호: {{ item.id }} / 제목:{{ item.title }} / 작성일:
        {{ item.created_at }} / 코멘트 수: {{ item.comments }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "IssueList",
  props: {
    list: Array,
  },
};
</script>
<style scoped lang="scss"></style>
