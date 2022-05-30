<template>
  <div>
    <app-header />

    <div class="box">
      <app-create-task />
    </div>

    <app-tasks
      v-for="(task, i) in tasks"
      :key="i"
      :task="task"
    />
  </div>
</template>

<script>
import { mapState } from 'vuex'
import AppTasks from '@/components/AppTasks.vue'
import AppHeader from '@/components/AppHeader.vue'
import AppCreateTask from '@/components/AppCreateTask.vue'

export default {
  name: 'IndexPage',
  components: {
    AppTasks,
    AppHeader,
    AppCreateTask
  },
  computed: {
    ...mapState(['tasks'])
  }
}
</script>
