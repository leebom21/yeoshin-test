<template>
  <div class="listWrap">
    <table class="tbList" cellpadding="15">
      <colgroup>
        <col width="10%" />
        <col width="60%" />
        <col width="18%" />
        <col width="11%" />
      </colgroup>
      <thead>
        <tr class="title">
          <th v-for="(trTitle, i) in title" :key="i">{{ trTitle }}</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in list" :key="item.id">
          <IssueListItem :item="item" />
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import IssueListItem from "../components/IssueListItem.vue";

export default {
  name: "IssueList",
  data() {
    return {
      title: ["NO", "제목", "작성일", "댓글 수"],
    };
  },
  components: { IssueListItem },
  props: {
    list: Array,
  },
};
</script>
<style scoped lang="scss">
.listWrap {
  display: grid;
  width: 70%;
  margin: 0 auto;
  border-radius: 7px;
  overflow: hidden;
  font-size: 14px;
  height: 76vh;
  overflow-y: scroll;

  .tbList {
    thead {
      background: #ff4493;
      color: #fff;
      tr {
        th {
          &:nth-child(4) {
            width: 11%;
          }
        }
      }
    }
    tbody {
      tr {
        border-bottom: 1px solid #f1f1f1;
      }
    }
  }
}
</style>
