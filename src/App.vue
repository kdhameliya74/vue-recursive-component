<template>
  <div id="app">
    <img alt="Vue logo" class="center" src="./assets/logo.png" width="25%" />
    <Recursive :categories="data" />
  </div>
</template>

<script>
import Recursive from "./components/Recursive";

export default {
  name: "App",
  components: {
    Recursive,
  },
  data() {
    return {
      data: [
        {
          id: 1,
          name: "category 1",
          children_data: [
            {
              id: 11,
              name: "category 1.1",
              children_data: [
                {
                  id: 111,
                  name: "category 1.1.1",
                  children_data: [
                    {
                      id: 1111,
                      name: "category 1.1.1.1",
                    },
                    {
                      id: 1112,
                      name: "category 1.1.1.2",
                    },
                  ],
                },
                {
                  id: 112,
                  name: "category 1.2.1",
                },
              ],
            },
            {
              id: 12,
              name: "category 1.2",
            },
            {
              id: 13,
              name: "category 1.3",
              children_data: [
                {
                  id: 131,
                  name: "category 1.3.1",
                },
              ],
            },
          ],
        },
        {
          id: 2,
          name: "category 2",
          children_data: [
            {
              id: 21,
              name: "category 2.1",
              children_data: [
                {
                  id: 211,
                  name: "category 2.1.1",
                },
                {
                  id: 212,
                  name: "category 2.1.2",
                },
              ],
            },
            {
              id: 22,
              name: "category 2.2",
            },
            {
              id: 23,
              name: "category 2.3",
            },
          ],
        },
        {
          id: 3,
          name: "category 3",
          children_data: [
            {
              id: 31,
              name: "category 3.1",
            },
          ],
        },
        {
          id: 4,
          name: "category 4",
        },
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>
