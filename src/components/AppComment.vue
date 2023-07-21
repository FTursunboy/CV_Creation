<template>
  <div>
    <div class="container">
      <p>
        <button @click="$emit('loadComments')" class="btn primary">Загрузить комментарии</button>
      </p>
      <div class="card">
        <h2>Комментарии</h2>
        <ul class="list">
          <li class="list-item" v-for="comment in comments" :key="comment.name">
            <div >
              <p><strong>{{comment.name}}</strong></p>
              <small>{{comment.text}}</small>
            </div>
          </li>
        </ul>
      </div>
      <div class="loader"></div>
    </div><div class="container">

  </div>
  </div>
</template>

<script>

export default {
  props: ['comments'],
  emits: ['loadComments']
}
</script>

<style scoped>

</style>