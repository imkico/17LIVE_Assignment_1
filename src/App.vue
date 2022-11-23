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
      data: [
        {
          name: "Anna",
          year: 10,
          class: "A",
        },
        {
          name: "Mark",
          year: 10,
          class: "M",
        },
      ],
    };
  },
  components: {
    List,
  },
};
</script>
