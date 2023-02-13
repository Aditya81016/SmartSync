<template>
  <div id="app">
    <RouterView :data="data" />
    <Footer />
  </div>
</template>

<script>
import { RouterLink, RouterView } from "vue-router";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    RouterView,
    Footer,
  },
  data() {
    return {
      data: {
        user_name: 'Pablo',
        notes: {
          all: [
            { title: "Note 1", content: "This is note 1" },
            { title: "Note 2", content: "This is note 2" },
            { title: "Note 3", content: "This is note 3" },
            { title: "Note 4", content: "This is note 4" },
            { title: "Note 5", content: "This is note 5" },
          ],
          recent: [
            { title: "Note 4", content: "This is note 4" },
            { title: "Note 5", content: "This is note 5" },
          ],
        },
        todos: {
          all: [
            {
              title: "Learn Vue",
              content:
                "Vue is a JavaScript library for building user interfaces.",
              tasks: [
                { task: "Task 1", status: false },
                { task: "Task 2", status: false },
                { task: "Task 3", status: false },
                { task: "Task 4", status: false },
                { task: "Task 5", status: false },
                { task: "Task 6", status: false },
              ],
            },
            {
              title: "Learn Vue Router",
              content:
                "Vue Router is a JavaScript library for building web applications.",
              tasks: [
                { task: "Task 1", status: false },
                { task: "Task 2", status: false },
                { task: "Task 3", status: false },
                { task: "Task 4", status: false },
              ],
            },
            {
              title: "Learn Vuex",
              content:
                "Vuex is a JavaScript library for managing application state.",
              tasks: [
                { task: "Task 1", status: false },
                { task: "Task 2", status: false },
                { task: "Task 3", status: false },
                { task: "Task 4", status: false },
              ],
            },
            {
              title: "Learn Vuex Store",
              content:
                "Vuex Store is a JavaScript library for managing application state.",
              tasks: [
                { task: "Task 1", status: false },
                { task: "Task 2", status: false },
                { task: "Task 3", status: false },
                { task: "Task 4", status: false },
              ],
            },
          ],
          recent: [
            {
              title: "Learn Vue",
              content:
                "Vue is a JavaScript library for building user interfaces.",
              tasks: [
                { task: "Task 1", status: false },
                { task: "Task 2", status: false },
                { task: "Task 3", status: false },
                { task: "Task 4", status: false },
                { task: "Task 5", status: false },
                { task: "Task 6", status: false },
              ],
            },
            {
              title: "Learn Vue Router",
              content:
                "Vue Router is a JavaScript library for building web applications.",
              tasks: [
                { task: "Task 1", status: false },
                { task: "Task 2", status: false },
                { task: "Task 3", status: false },
                { task: "Task 4", status: false },
              ],
            },
          ]
        },
      },
    };
  },

  mounted() {
    if (this.data.notes.all.length === 0)
      this.data.notes.all = [{ title: "No Notes", content: "create a new note" }];

    if (this.data.todos.all.length === 0)
      this.data.todos.all = [{ title: "No Todos", content: "create a new Todo" }];
  },
};
</script>

<style scoped></style>
