<template>
  <div v-if="listType === 1" class="type1 list-wrapper">
    <ul>
      <li v-for="item in data" :key="item.name">
        Student: {{ item.name }}<br />
        Year: {{ item.year }}, Room: {{ item.class }}
      </li>
    </ul>
  </div>
  <div v-if="listType === 2" class="type2 list-wrapper">
    <ul>
      <li v-for="item in data" :key="item.title">
        Title: {{ item.title }}<br />
        Category: {{ item.category }} | {{ item.rating }} likes
      </li>
    </ul>
  </div>
  <div v-if="listType === 3" class="type3 list-wrapper">
    <h1>Top 3 Winners</h1>
    <ul>
      <li v-for="item in data" :key="item.rank">
        {{ item.rank }} {{ item.winner }}
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
