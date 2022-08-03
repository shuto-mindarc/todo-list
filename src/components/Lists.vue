<template>
  <div v-for="(task, index) in tasks" :key="index" class="card my-2">
    <div class="card-body py-0 px-2">
      <ul class="list-group list-group-horizontal rounded-0 bg-transparent">
        <li
          class="list-group-item px-3 py-1 d-flex align-items-center flex-grow-1 border-0 bg-transparent"
        >
          <p class="lead fw-normal mb-0">
            {{ task }}
          </p>
        </li>
        <li
          class="list-group-item ps-3 pe-0 py-1 rounded-0 border-0 bg-transparent"
        >
          <div class="d-flex flex-row justify-content-end mb-1">
            <button class="btn btn-danger" @click="removeTask(index)">X</button>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import ref from "vue";

export default {
  props: ["tasks"],
  setup(props) {
    const removeTask = (index) => {
      props.tasks.splice(index, 1);
    };

    return {
      removeTask,
    };
  },
};
</script>

<style></style>
