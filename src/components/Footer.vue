<template>
  <footer>
    <div class="special" id="special" ref="special">
      <div id="blob-before"></div>
      <div id="blob-after"></div>
      <div id="blob"></div>
    </div>
    <button v-on:click="moveTowards($event)" class="Home Button active">
      <IconHome />
    </button>
    <button v-on:click="moveTowards($event)" class="Notes Button">
      <IconNotes />
    </button>
    <button v-on:click="moveTowards($event)" class="Add Button">
      <IconAdd />
    </button>
    <button v-on:click="moveTowards($event)" class="Tasks Button">
      <IconTasks />
    </button>
    <button v-on:click="moveTowards($event)" class="Settings Button">
      <IconSettings />
    </button>
  </footer>
</template>

<script>
import IconHome from "./icons/IconHome.vue";
import IconNotes from "./icons/IconNotes.vue";
import IconAdd from "./icons/IconAdd.vue";
import IconTasks from "./icons/IconTasks.vue";
import IconSettings from "./icons/IconSettings.vue";

export default {
  name: "Footer",
  components: {
    IconHome,
    IconNotes,
    IconAdd,
    IconTasks,
    IconSettings,
  },

  methods: {
    moveTowards(event) {
      let ele = event.target;
      if (ele.classList.contains("Path")) ele = ele.parentElement;
      if (ele.classList.contains("SVG")) ele = ele.parentElement;
      if (ele.classList.contains("Button")) {
        document.getElementsByClassName("special")[0].style.left =
          ele.getBoundingClientRect().left - 17.5 + "px";
        document.getElementsByClassName("active")[0].classList.remove("active");
        ele.classList.add("active");

        if (ele.classList.contains("Home")) this.$router.push("/");
        else if (ele.classList.contains("Notes")) this.$router.push("/notes");
        else if (ele.classList.contains("Add")) this.$router.push("/add");
        else if (ele.classList.contains("Tasks")) this.$router.push("/todos");
        else if (ele.classList.contains("Settings")) this.$router.push("/settings");
      }
    },
  },

  data() {
    return {
      special: document.getElementById("special"),
    };
  },

  mounted() {
    let active = document.getElementsByClassName("active")[0];
    let special = document.getElementsByClassName("special")[0];
    special.style.left = active.getBoundingClientRect().left - 12 + "px";
  },
};
</script>

<style scoped>
/* * {
    outline: auto;
} */

footer {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100vw;
  height: 50px;
  padding: 10px;
  background-color: rgb(46, 47, 48);
  display: flex;
  justify-content: space-evenly;
  align-items: center;
}

button {
  width: 30px;
  height: 30px;
  background-color: transparent;
  border-radius: 100%;
  border: none;
  transform: scale(1.2);
  transition: all 0.3s ease-in-out;
}

#special {
  position: absolute;
  bottom: 10px;
  transform: translate(0px, 0);
  transition: all 0.25s ease;
}

#blob {
  position: relative;
  width: 70px;
  height: 70px;
  background-color: rgb(240, 84, 84);
  border-radius: 50%;
  border: 7.5px solid rgb(18, 18, 18);
  box-shadow: 0px 10px 15px -3px rgb(255, 0, 0);
}

#blob-before,
#blob-after {
  content: "";
  position: absolute;
  width: 30px;
  height: 30px;
  /* background-color: white; */
  background-color: rgb(46, 47, 48);
  border-radius: 50%;
}

#blob-before {
  top: 26px;
  left: -24px;
  border-right: 10px solid rgb(18, 18, 18);
  transform: rotate(-47.5deg);
}

#blob-after {
  top: 26px;
  right: -24px;
  border-left: 10px solid rgb(18, 18, 18);
  transform: rotate(47.5deg);
}

.active {
  transform: scale(1.6);
  margin-bottom: 37.5px;
}
</style>
