<template>
  <b-field position="is-centered">
    <b-input
      v-model.trim="newTask"
      type="text"
      placeholder="Add a new task"
    />
    <p class="control">
      <b-button
        class="button is-info"
        @click="addTask"
      >
        Add
      </b-button>
    </p>
  </b-field>
</template>

<script>
import { mapMutations } from 'vuex'

export default {
  name: 'AppCreateTask',
  data: () => ({
    newTask: ''
  }),
  methods: {
    ...mapMutations({
      add: 'ADD_TASK'
    }),
    addTask () {
      if (this.newTask) {
        this.add(this.newTask)
        this.newTask = ''
      }
    }
  }
}
</script>
