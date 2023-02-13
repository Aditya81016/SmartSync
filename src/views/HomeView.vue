<template>
  <main>
    <div class="blur a"></div>
    <h1>Hi {{ data.user_name }}</h1>
    <SearchBar />
    <br />
    <h3>Recent Notes</h3>
    <ol class="carsoule">
      <li v-for="note in data.notes.recent" :key="note">
        <div class="box">
          <h6 class="title text-wrap">{{ note.title }}</h6>
          <hr />
          <p class="content text-wrap">{{ note.content }}</p>
        </div>
      </li>
    </ol>
    <h3>Recent Todos</h3>
    <ol>
      <li v-for="todo in data.todos.recent" :key="todo">
        <div class="rect">
          <div class="d-flex gap-3">
            <input type="checkbox" name="checkbox" id="checkbox" />
            <h6 class="title text-wrap">{{ todo.title }}</h6>
          </div>
          <hr />
          <p style="margin: -10px 0 0 0" class="content text-wrap">
            {{ todo.content }}
          </p>
        </div>
      </li>
    </ol>
  </main>
</template>

<script>
import SearchBar from "../components/SearchBar.vue";
import App from "../App.vue";

export default {
  name: "HomeView",
  components: {
    SearchBar,
  },
  props: {
    data: { type: Object, required: true },
  },
};
</script>

<style scoped>
main {
  margin: 0px;
  padding: 20px;
  height: 90vh;
  overflow-y: scroll;
  /* outline: auto; */
}
/* 
main::-webkit-scrollbar {
  width: 0px;
}

main::-webkit-scrollbar-track {
  background: #202020;
}

main::-webkit-scrollbar-thumb {
  background: #4b4b4b;
} */

h1,
h3 {
  margin: 0 0 20px 10px;
}

h6 {
  margin: 0 0 -10px;
}

ol {
  list-style: none;
}
.carsoule {
  display: flex;
  gap: 40px;
  overflow-x: scroll;
  height: 250px;
}

.box {
  width: 150px;
  height: 200px;
  padding: 20px;
  border-radius: 20px;
  border: 2px solid #4b4b4b;
  background-color: #202020;
  box-shadow: 0px 10px 20px 0px rgb(0, 0, 0);
}

.rect {
  width: 100%;
  padding: 20px;
  border-radius: 20px;
  border: 2px solid #4b4b4b;
  background-color: #202020;
  margin: 0 0 20px 0;
  box-shadow: 0px 10px 20px 0px rgb(0, 0, 0);
}

#checkbox {
  border-radius: 50%;
}


.blur.a {
  top: 0px;
  left: 0px;
}
</style>
