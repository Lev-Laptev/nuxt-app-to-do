<template>
  <div class="tasks">
    <AppBox
      class="mb-5"
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
    </AppBox>
  </div>
</template>

<script>
import { mapMutations } from 'vuex'
import { AppBox } from '@/components/common'
import { TYPE_OBJECT } from '@/constants/types'

export default {
  name: 'AppTasks',
  components: { AppBox },
  props: {
    task: {
      type: TYPE_OBJECT,
      default: () => ({})
    }
  },
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
