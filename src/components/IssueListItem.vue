<template>
  <div>
    <td>
      {{ item.id }}
    </td>
    <td>
      {{ item.title }}
    </td>
    <td>
      {{ dateFormat(item.created_at) }}
    </td>
    <td>
      {{ item.comments }}
    </td>
  </div>
</template>

<script>
import dayjs from "dayjs";
export default {
  name: "IssueListItem",
  props: {
    item: Object,
  },
  methods: {
    dateFormat: (str) => {
      return str ? dayjs(str, "YYYYMMDDHHmmss").format("YYYY.MM.DD") : "-";
    },
  },
};
</script>
<style scoped lang="scss">
div {
  width: 100%;
  display: contents;

  td {
    vertical-align: middle;
  }
}
</style>
