<template>
  <form @submit="onSubmit" class='add-form'>
    <div class='form-control'>
      <label>업무</label>
      <input type="text" v-model="text" name="text" placeholder="할 일 추가"/>
    </div>
    <div class='form-control'>
      <label>날짜 & 시간</label>
      <input type='text' v-model="day" name='day' placeholder="시간/날짜 추가">
    </div>
    <div class='form-control form-control-check'>
      <label>알림설정</label>
      <input type="checkbox" v-model="reminder" name="remainder"/>
    </div>
    <input type="submit" value="할 일 저장하기" class='btn btn-block'/>
  </form>
</template>

<script>
export default {
  name: 'AddTask',
  data() {
    return {
      text: '',
      day: '',
      reminder: false
    }
  },
  methods: {
    onSubmit(e) {
      e.preventDefault()

      if (!this.text) {
        alert('Please add a task')
        return
      }

      const newTask = {
        // id: Math.floor(Math.random() * 10000),
        text: this.text,
        day: this.day,
        reminder: this.reminder

      }
      this.$emit('add-task', newTask)

      this.text = ''
      this.day = ''
      this.reminder = true
    }
  }
}
</script>

<style scoped>
  .add-form {
    margin-bottom: 40px;
  }

  .form-control {
    margin: 15px 0;
  }

  .form-control label {
    display: block;
    margin-left: 5px;
  }
  .form-control input {
    width: 100%;
    height: 40px;
    margin: 5px;
    padding: 3px 7px;
    font-size: 17px;
  }

  .form-control-check {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .form-control-check label{
    flex:1;
  }
  .form-control-check input{
    flex: 2;
    height:20px;
  }

</style>