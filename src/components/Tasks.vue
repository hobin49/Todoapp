<template>
  <div :key="task.id" v-for="task in tasks">
    <TaskMain @toggle-reminder="$emit('toggle-reminder', task.id)" @delete-task="$emit('delete-task', task.id)" :task='task' />
  </div>
</template>

<script>
import TaskMain from './Task'

export default {
  name: 'TaskS',
  props: {
    tasks: Array
  },
  components: {
    TaskMain
  },
  emits: ['delete-task', 'toggle-reminder']
}
</script>