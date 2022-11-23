<template>
  <div>
    <ul v-if="listType === 1">
      <li v-for="item in data" :key="item.name" class="list1">
        {{ item.name }} - {{ item.year }} - {{ item.class }}
      </li>
    </ul>
    <ul v-else-if="listType === 2">
      <li v-for="item in data" :key="item.title">
        {{ item.title }} - {{ item.category }} - {{ item.rating }}
      </li>
    </ul>
    <ul v-else-if="listType === 3">
      <li v-for="item in data" :key="item.rank">
        {{ item.rank }} - {{ item.winner }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "List",
  props: {
    data: {
      type: Array,
      required: true,
    },
  },
  computed: {
    listType() {
      if (this.data.length === 0) {
        return null;
      }
      if (typeof this.data[0].name !== "undefined") {
        return 1;
      } else if (typeof this.data[0].title !== "undefined") {
        return 2;
      } else if (typeof this.data[0].winner !== "undefined") {
        return 3;
      } else {
        return null;
      }
    },
  },
};
</script>
