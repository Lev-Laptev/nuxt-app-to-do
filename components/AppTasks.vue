<template>
  <div class="tasks">
    <div
      class="box mb-5"
      :class="completeTask"
    >
      <div class="content is-medium">
        <p>{{ task.content }}</p>
      </div>

      <div class="field is-grouped">
        <p class="control">
          <button
            class="button is-info is-small is-rounded"
            @click="toggleDone"
          >
            {{ buttonText }}
          </button>
        </p>
        <p class="control">
          <button
            class="button is-danger is-small is-rounded"
            @click="removeTask"
          >
            Delete
          </button>
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'

export default {
  name: 'AppTasks',
  props: ['task'],
  computed: {
    buttonText () {
      return this.task.done ? 'Undo' : 'Done'
    },
    completeTask () {
      return this.task.done ? 'has-background-success-light' : ''
    }
  },
  methods: {
    ...mapMutations({
      toggle: 'TOGGLE_TASK',
      remove: 'REMOVE_TASK'
    }),
    toggleDone () {
      this.toggle(this.task)
    },
    removeTask () {
      this.remove(this.task)
    }
  }
}
</script>
