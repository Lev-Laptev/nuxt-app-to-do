<template>
  <AppBox>
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
  </AppBox>
</template>

<script>
import { mapMutations } from 'vuex'
import { AppBox } from '@/components/common'

export default {
  name: 'AppCreateTask',
  components: {
    AppBox
  },
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
