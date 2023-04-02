<template>
  <div id="app">
    <List :data="data" />
  </div>
</template>
<script>
import List from "./components/List.vue";

export default {
  data() {
    return {
      // data: [
      //   {
      //     name: "Anna",
      //     year: 10,
      //     class: "A",
      //   },
      //   {
      //     name: "Mark",
      //     year: 10,
      //     class: "M",
      //   },
      // ],
      // data: [
      //   {
      //     title: "Javascript Info",
      //     category: "book",
      //     rating: 10,
      //   },
      //   {
      //     title: "Fantasy",
      //     category: "movie",
      //     rating: 5,
      //   },
      // ],
      data: [
        {
          winner: "Amy",
          rank: 1,
        },
        {
          winner: "Bob",
          rank: 2,
        },
        {
          winner: "Jack",
          rank: 3,
        },
      ],
    };
  },
  components: {
    List,
  },
};
</script>
