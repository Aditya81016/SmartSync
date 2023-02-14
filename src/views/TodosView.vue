<template>
  <main>
    <h1>Your Todos</h1>
    <ol>
      <li v-for="todo in data.todos.all" :key="todo">
        <div class="box">
          <h6 class="title text-wrap">{{ todo.title }}</h6>
          <hr />
          <p class="content text-wrap">{{ todo.content }}</p>
        </div>
      </li>
    </ol>
  </main>
</template>

<script>
export default {
  name: "Tasks",
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

h1,
h3 {
  margin: 0 0 20px 10px;
}

ol {
  list-style: none;
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: space-evenly;
  padding: 0;
}

li {
  width: 100%;
}

.box {
  width: 100%;
  height: 200px;
  padding: 20px;
  border-radius: 20px;
  border: 2px solid #4b4b4b;
  background-color: #202020;
  box-shadow: 0px 10px 20px 0px rgb(0, 0, 0);
  /* margin: 0 0 0 -30px; */
}
</style>
