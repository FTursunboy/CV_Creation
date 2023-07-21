<template>
  <div class="card card-w70" v-if="title || avatar || subtitle || text1">
    <h1>{{title}}</h1>
    <div class="avatar">
      <img :src="avatar">
    </div>
    <h2>{{subtitle}}</h2>
    <p>
    {{text1}}
  </p>
  </div>
  <div v-else class="card card-w70">
  <h3 >Добавьте первый блок, чтобы увидеть результат</h3>
  </div>
</template>

<script>
export default {
  props: ['text1', 'title', 'subtitle', 'avatar'],
  data() {
    return {
      images: [],
      zag: [],
      pod: [],
      text: []

    }
  },


  methods: {

  }

}
</script>

<style scoped>

</style>