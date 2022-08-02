<template>
  <div class="pb-2">
    <div class="card">
      <div class="card-body">
        <div class="d-flex flex-row align-items-center">
          <input
            type="text"
            class="form-control form-control-lg"
            id="exampleFormControlInput1"
            placeholder="Add new..."
            v-model="input"
          />
          <div>
            <button type="button" class="btn btn-primary ms-2" @click="addTask">
              Add
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
  <hr class="my-4" />
</template>

<script>
import { ref } from "vue";

export default {
  props: ["tasks"],
  setup(props) {
    const input = ref("");

    const addTask = () => {
      if (input.value !== "") {
        props.tasks.push(input.value);
      }
      input.value = "";
    };

    return {
      input,
      addTask,
    };
  },
};
</script>

<style></style>
