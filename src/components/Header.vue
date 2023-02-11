<template>
  <header>
    <h1>{{ title }}</h1>
    <ButtonS @btn-click="$emit('toggle-add-task')" :text="showAddTask ? '닫기' : '추가하기'" :color="showAddTask ? 'red' : 'green'"/>
  </header>
</template>

<script>
import ButtonS from './Button'

export default {
  name: 'HeaderV',
  props: {
    title: String,
    showAddTask: Boolean
  },
  components: {
    ButtonS
  }
}
</script>

<style scoped>
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
  }
</style>
