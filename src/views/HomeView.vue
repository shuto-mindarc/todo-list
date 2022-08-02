<template>
  <div class="container todo__list">
    <div class="card">
      <div class="card-body py-4 px-4 px-md-5">
        <p class="h1 text-center mt-3 mb-4 pb-3 text-primary">
          <i class="fas fa-check-square me-1"></i>
          <u>My Todo List</u>
        </p>
        <NewTask :tasks="tasks" />
        <Lists :tasks="tasks" />
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import NewTask from "../components/NewTask.vue";
import Lists from "../components/Lists.vue";

export default {
  name: "HomeView",
  components: {
    NewTask,
    Lists,
  },
  setup() {
    const tasks = ref(["wash dishes", "feed bunny"]);

    return {
      tasks,
    };
  },
};
</script>

<style>
.todo__list {
  width: 100%;
  max-width: 45rem !important;
  padding: 1em;
  margin: 1em auto;
  overflow: auto;
  background-color: white;
  box-shadow: 0px 0.25rem 1rem;
}
</style>
