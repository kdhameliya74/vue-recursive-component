<template>
  <ul class="nested">
    <template v-if="categories.length">
      <li
        v-for="category of categories"
        :key="category.id"
        :style="{ color: color }"
      >
        {{ category.name }}
        <template v-if="category.children_data">
          <Recursive
            :color="getRandomColor()"
            :categories="category.children_data"
          />
        </template>
      </li>
    </template>
  </ul>
</template>
<script>
export default {
  name: "Recursive",
  props: {
    categories: {
      type: Array,
      default: () => [],
    },
    color: {
      type: String,
      default: null,
    },
  },
  methods: {
    getRandomColor() {
      var letters = "0123456789ABCDEF";
      var color = "#";
      for (var i = 0; i < 6; i++) {
        color += letters[Math.floor(Math.random() * 16)];
      }
      return color;
    },
  },
};
</script>
<style scoped>
ul.nested {
  margin: 0;
  padding: 5px 20px;
  width: 100%;
}
ul li {
  margin-top: 5px;
  margin-bottom: 5px;
}
</style>
