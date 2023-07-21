<template>

    <form class="card card-w30" @submit.prevent="submitForm">
      <div class="form-control">
        <label for="type">Тип блока</label>
        <select v-model="title" id="type">
          <option value="title" >Заголовок</option>
          <option  value="subtitle">Подзаголовок</option>
          <option  value="avatar">Аватар</option>
          <option value="text">Текст</option>
        </select>
      </div>

      <div class="form-control">
        <label for="value">Значение</label>
        <textarea v-model="text" id="value" rows="3"></textarea>
      </div>

      <button :disabled="!isValid" class="btn primary">Добавить</button>
    </form>

</template>

<script>
export default {
    data() {
      return {
        title: 'title',
        text: ''
      }
    },

  computed: {
    isValid() {
      return this.text.length > 3
    }
  },
  methods: {
    submitForm() {
      this.$emit('form_enter', {
        title: this.title,
        text: this.text,
      })

      this.title = 'title'
      this.text = ''
    }
  }
}
</script>

<style scoped>

</style>